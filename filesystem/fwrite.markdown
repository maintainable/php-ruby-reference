# fwrite

To write data to a file in PHP, we call the `fwrite` function, passing it a
stream resource and the data to write.

{{code:php
    $f = fopen('/path/to/foobar', 'w');
    fwrite($f, 'chars');
    fclose($f);
}}

To write data to a file in Ruby, we first get a `File` instance and then call
the `File#write` instance method.

{{code:ruby
    File.open('/path/to/foobar', 'w') do |f|
      f.write 'chars'
    end
}}


{{related:
    filesystem/fread
    filesystem/fopen
    filesystem/fsockopen
    filesystem/popen
    filesystem/file_get_contents
}}
