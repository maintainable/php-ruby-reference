# fputs

`fputs` -- Alias of [fwrite](../filesystem/fwrite)

In PHP, `fwrite` and `fputs` are equivalent.

{{code:php
    $f = fopen('/path/to/foobar', 'w');

    # identical
    fwrite($f, 'chars');
    fputs($f, 'chars');

    fclose($f);
}}

Ruby's `File` objects, and all Ruby objects that include the `IO` mixin, have
instance methods `write` and `puts`. Unlike PHP, they are not equivalent.

{{code:ruby
    File.open('/path/to/foobar', 'w') do |f|
      f.write("foo")    # writes "foo"
      f.write("foo\n")  # writes "foo\n"

      f.puts("foo")     # writes "foo\n"
      f.puts("foo\n")   # writes "foo\n"
    end
}}

As shown by the example above, Ruby's `File#write` method does not append
newlines. This is the familiar behavior from PHP's `fwrite` and `fputs`.

Ruby's `File#puts` method behaves differently. It will always append a newline
to any line that does not already end in one.

{{related:
    filesystem/fwrite
}}
