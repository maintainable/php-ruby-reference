# rewind

The `rewind` function in PHP resets the file pointer back to the start of the
file. This example does a dummy read on the file to move the pointer and then
rewinds it.

{{code:php
    $f = fopen('/path/to/foobar.txt', 'r');
    fread($f);
    print ftell($f);
    //=> 42

    rewind($f);
    print ftell($f);
    //=> 0

    fclose($f);
}}

Ruby's `File#rewind` method works exactly the same way.

{{code:ruby
    File.open('/path/to/foobar.txt', 'r') do |f|
      f.read
      puts f.tell
      #=> 42

      f.rewind
      puts f.tell
      #=> 0
    end
}}


{{related:
    filesystem/fseek
    filesystem/ftell
}}
