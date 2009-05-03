We use the `ftruncate` function in PHP to truncate a file to a given length.


{{code:php
    $f = fopen('/path/to/foobar', 'w')
    ftruncate($f, 10);
    fclose($f);
}}

The same task can be accomplished in Ruby with the `File#truncate` method:

{{code:ruby
    File.open('/path/to/foobar', 'w') do |f|
      f.truncate(10)
    end
}}

Ruby also provides the `File.truncate` class method for convenience. It allows
you to truncate a file without opening it yourself.

{{code:ruby
    File.truncate('/path/to/foobar', 10)
}}


{{related:
    filesystem/fopen          
    filesystem/fseek
}}
