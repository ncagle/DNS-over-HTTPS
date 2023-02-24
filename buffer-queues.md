I propose to implement a "buffer queue" as sketched out below.

We have either `dynbuf` or buffers that are managed "manually". While `dynbuf` is nice, for IO buffering it has two drawbacks. 
It reallocs when growing and, more significantly, it self-destructs on adding more data than it is configured for.

What we lack is a buffer that allows reads and writes without being empty. Sometimes `dynbuf` is used with a separate `readlen` var that tracks how much of the buffered data we already have handled. This is brittle.

```c
struct buf_chunk {
  struct buf_chunk *next;
  size_t dlen;
  size_t r_offset;
  size_t w_offset;
  const unsigned char data[1];
};

struct bufq {
  struct buf_chunk *head;
  struct buf_chunk *tail;
  struct buf_chunk *spare;
  size_t chunk_count;
  size_t max_chunks;
  size_t chunk_size;
};

/**
 * Initialize a buffer queue that can hold up to `max_chunks` buffers
 * each of size `chunk_size`.
 */
void Curl_bufq_init(struct bufq *q, size_t chunk_size, size_t max_chunks);

void Curl_bufq_reset(struct bufq *q); /* clear, buf keep buffer */
void Curl_bufq_free(struct bufq *q);  /* free all */
size_t Curl_bufq_len(struct bufq *q); /* length of buffered data */

```
With simple read/write method in the usual signatures:

```c
ssize_t Curl_bufq_write(struct bufq *q, const char *data, size_t len,
                        CURLcode *err);
ssize_t Curl_bufq_read(struct bufq *q, char *data, size_t len,
                        CURLcode *err);
```

And maybe something more sophisticated like

```c
typedef ssize_t Curl_bufq_writer(void *writer_ctx,
                                 const char *data, size_t len,
                                 CURLcode *err);
ssize_t Curl_bufq_pass(struct bufq *q, Curl_bufq_writer *writer,
                       void *writer_ctx, CURLcode *err);
```

and the companion:

```c
typedef ssize_t Curl_bufq_reader(void *reader_ctx,
                                 char *data, size_t len,
                                 CURLcode *err);
ssize_t Curl_bufq_slurp(struct bufq *q, Curl_bufq_reader *reader,
                        void *reader_ctx, CURLcode *err);
```
If proving useful, we may add variations that `slurp` until a certain amount of data is available. Or `pass` a maximum amount, etc.
