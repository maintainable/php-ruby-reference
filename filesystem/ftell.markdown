# ftell

We use PHP's `ftell` function to return the current position of a file
pointer.

{{code:php
    $f = fopen('/path/to/foobar', 'r');
    fseek($f, 2);
    print ftell($f);
    //=> 2
    fclose($f);
}}

The `File#tell` instance method works exactly the same way.

{{code:ruby
    File.open('/path/to/foobar', 'r') do |f|
      f.seek 2
      puts f.tell
      #=> 2
    end
}}

Ruby IO objects also provide the aliases `pos` and `pos=` for working with the
file pointer's position. It's a common Ruby idiom to use these instead of
`seek` and `tell`, but you'll find both are widely used.

{{code:ruby
    File.open('/path/to/foobar', 'r') do |f|
      f.pos = 2
      puts f.pos
      #=> 2
    end
}}


{{related:
    filesystem/fopen
    filesystem/popen
    filesystem/fseek          
    filesystem/rewind
}}
