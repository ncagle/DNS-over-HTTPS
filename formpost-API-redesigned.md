# Background

The `curl_formadd()` API is...
 - complicated (multitple varargs, several ways to do the same thing)
 - error-prone (due to the above)
 - the use of the public struct makes it hard to change - and yet hardly any users actually create the linked list of headers themselves!

# Alternative take

Deprecate the old functions and the use of `CURLOPT_HTTPPOST` (but expect that users will keep using them for a very long time ahead). The new API needs to be feature-complete with the old.

`curl_form_init()` creates a new form post instance and returns an opaque handle to it. 

`curl_form_addpart(form)` creates a new (empty) part to the multipart formpost and adds that part to the existing form passed in as argument.

There's then a set of functions to set properties for the added part. `curl_form_set_name()` and `curl_form_set_data()` the two most obvious ones. They can pass in -1 for length to have the function do strlen() on them, or set the data length in the 3rd argument.

Here's a basic example creating a form, adding two parts and then sending it.

    curl_form *form = curl_form_init();
    curl_formpart *part = curl_form_addpart(form);
    curl_form_set_name(part, "name", -1);
    curl_form_set_data(part, "Daniel", -1);

    part = curl_form_addpart(form);
    curl_form_set_name(part, "shoesize", 8);
    curl_form_set_data(part, "10000", 5);

    CURLcode rc = curl_easy_setopt(easy, CURLOPT_FORMPOST, form);
    curl_form_cleanup(form);

### File uploads

To send "file", use `curl_form_set_file` instead of `curl_form_set_data`

    curl_form_set_name(part, "upload", -1);
    curl_form_set_file(part, "/tmp/upload.tar.gz", 0, NULL);

To instead "upload" the file from a local buffer and setting a made up file name for it:

    curl_form_set_name(part, "upload", -1);
    curl_form_set_file(part, buffer, buflen, "made-up-name");

### Custom content-type and headers for a specific part

To set the Content-Type: header specifically, offer this shortcut:

    curl_form_set_type(part, "text/html");

... or to set any custom headers for the part, create a linked slist of headers and provide that:

    curl_form_set_headers(part, slist); /* standard created list */

## Remove support for

 - CURLFORM_PTRCONTENTS and CURLFORM_PTRNAME, always copy.
 - CURLFORM_ARRAY, too complex
 - CURLFORM_CONTENTSLENGTH, use 64bit CONTENTLEN
