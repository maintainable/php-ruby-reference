# feof

The `feof` function tests if a file pointer has reached end of file (EOF).

This example demonstrates by making a dummy read, which places the pointer at
the end of the file. The result of `feof` is then `true`.

{{code:php
    $f = fopen('/path/to/foobar', 'r');
    fread($f);

    var_export( feof($f) );
    //=> true

    fclose($f);
}}

In Ruby, the `File#eof` instance method works the same way.

{{code:ruby
    File.open('/path/to/foobar', 'r') do |f|
      f.read

      p f.eof
      #=> true
    end
}}

The `File#eof` instance method is also aliased as `File#eof?`. It's a common
Ruby idiom for methods that return boolean be written like this, as if asking
a question.

Both `File#eof` and `File#eof?` are commonly used, so choose the one that is
most expressive for your usage.
