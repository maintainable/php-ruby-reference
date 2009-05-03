# file

Ruby's `File.readlines` method can be used in most common situations as a
replacement for PHP's `file` function.

{{code:php
    $lines = file('/path/to/foobar');
    var_export($lines);

    // => array(0 => 'hello\n', 1 => 'there')
}}

{{code:ruby
    lines = File.readlines('/path/to/foobar')
    p lines

    # => ['hello\n', 'there']
}}

Notice above that both PHP's `file` function and Ruby's `File.readlines`
method both return the line separators at the end of each array element. The
`file` function has a second optional argument, `flags`, that accepts
constants like `FILE_IGNORE_NEW_LINES`. In Ruby, you'll need to do this
filtering yourself.

A second important difference is that `File.readlines` has a second optional
argument, `separator`, that defaults to `\n`. This is quite different from
PHP, where PHP determines the separator based on the operating system or the
`auto_detect_line_endings` runtime configuration option.

## Iterating Over Lines

Often times you want to iterate over each line in a file and perform an
operation using the line. You can use Ruby's `File.readlines` to read the
lines into an array and then iterate over that array. However, this can be
costly when working with large files.

A better solution for these circumstances is to open a `File` instance and
then pass a block to the `each_line` method.

{{code:ruby
    File.open('/path/to/foobar') do |file|
  
      file.each_line do |line|
        puts line
      end

    end
}}

The snippet above will only read one line of the file into memory at a time,
whereas `File.readlines` will load the entire file into an array.

{{related:
    filesystem/readfile
    filesystem/fopen
    filesystem/fsockopen
    filesystem/popen
    filesystem/file_get_contents
    filesystem/include
    filesystem/stream_context_create
}}
