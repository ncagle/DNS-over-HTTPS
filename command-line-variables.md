*idea brain-storming area*

## --expand-[option]

`--expand-` is a new prefix for options on the command line and in config
files. If this prefix is used to a command line option, it means that the
value allows for variable expansion.

When expanding variables, the syntax to expand them is with `{{name}}` that
then inserts the contents of the specific variable instead. The expansion can
also insert an environment variable using the extended syntax `{{env:name}}`.

If no expansion is performed for a `--expand-` option, a warning will be
displayed.

Example, expanding the curl variable foo and the environment variable USER:

    --expand-url "https://example.org/{{foo}}/{{env:USER}}"

## --variable

The command line option `--variable [name=data]` sets internal curl variables
to have names with contents. This option can be used on the command line and
in config files of course, any number of times.

This option is order-sensitive in that it has a meaning on where in the chain
of options it is placed on the command line or config file. It sets the
variable content at that point in the command line and will then be set for
the following options.

The variable option itself can be expanded if used with a `--expand-` prefix.

Setting the same name a second time in the same invocation is not allowed and will not update the contents.

A variable name consists only of the characters "a-zA-Z0-9_", and may not be longer than 128 bytes.

The `data` for a variable can be porovide different ways:

### `"contents"`

Specifies that exact data in a string. The double quotes around the data may
be omitted, but that might make the data risk getting treated as something
else.

### `@filename`

The data will be read from the given file name.

### `@-`

The data will be read from stdin.

## Complete examples

Get the contents from the file "$HOME/.file" and use it as a directory name when requesting a URL, add the user name as a file name.

    curl \
    --expand-variable foo=@{{env:HOME}}/.file \
    --expand-url "https://example.org/{{foo}}/{{env:USER}}"

Pass a secret key to curl via a pipe:

    printf %s "$secret" |
    curl -g \
    --variable secret=@- \
    --expand-url 'https:/example.org/{{secret}}/method'