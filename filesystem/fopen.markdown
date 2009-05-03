# fopen

In PHP, the `fopen` function opens a file and returns a stream resource.  

{{code:php
    $f = fopen('/path/to/foobar', 'w');
    fwrite($f, 'chars');
    fclose($f);
{{

Above, the stream resource is placed in the variable `$f`. This resource is
then passed to other functions, such as `fread` and `fwrite`.

In Ruby, the `File.open` method returns a `File` instance. You can then call
methods like `read` and `write` on that instance.

{{code:ruby
    f = File.open('/path/to/foobar', 'w');
    f.write 'chars'
    f.close
}}

## Importance of Closing Files

It's a best practice in PHP to close any files that you open, as shown in the
example above. However, PHP does allow us to get away with being sloppy. PHP
is built around the notion of scripts executing within an HTTP request, and at
the end of that request it performs cleanup operations. One of the things that
PHP will do for you is close any resources that you have not destroyed.

Ruby, which is a more general purpose language that is not architected around
the notion of a HTTP request, does not perform this cleanup for you. This is
true even within the context of the Rails framework.

If you open files without closing them in a Rails application, the file
handles will be left open. You will accumulate them on each request and
eventually cause resource starvation.

## Passing a Block to File.open

Ruby's closures provide another way to open a file. You can pass a block to
the `File.open` method:

{{code:ruby
    File.open('/path/to/foobar', 'w') do |f|
      f.write 'chars'
    end
}}

When the block exits, the file will automatically be closed.  

It is considered a best practice in Rails applications to always perform file
operations this way to ensure no file handles are orphaned.

## Opening URLs

Underlying all file operations in PHP is the [streams
layer](http://www.php.net/stream). The streams layer provides a unified way to
access filesystem, network, and other resources. PHP functions like `fopen`
and `fwrite` can operate on the filesystem but can also transparently operate
on other types of resources that are supported by either the streams layer
itself or your own stream wrappers written in PHP.

For example, if PHP configuration directive `allow_url_fopen` is enabled, you
can use functions like `fopen` to make HTTP requests:

{{code:php
    $f = fopen('http://railsforphp.com');
    echo stream_get_contents($f);
    fclose($f);
}}

You could also use `file_get_contents` to perform the same operation in fewer
lines.

Ruby is similar to PHP in that it also abstracts operations behind its 
[IO subsystem](http://www.ruby-doc.org/core/classes/IO.html).  This,
combined with Ruby's open classes, also allow you to build powerful
abstractions much like PHP's stream wrappers.

For example, the `open-uri` library from the Ruby Standard Library allows you
to access HTTP resources.

{{code:ruby
    require 'open-uri'

    Kernel.open('http://railsforphp.com/') do |f|
      p f.read
    end
}}

Generally speaking, Ruby's IO implementation and bundled libraries have
similar potential to the PHP streams layer. That said, you may find that
Ruby's convenience and built-in support for different protocols is lacking
compared to PHP streams.

{{related:
    filesystem/fclose
    filesystem/fgets
    filesystem/fread
    filesystem/fsockopen
    filesystem/file
    filesystem/file_exists
    filesystem/is_readable
    filesystem/stream_set_timeout
    filesystem/popen
    filesystem/stream_context_create
}}
