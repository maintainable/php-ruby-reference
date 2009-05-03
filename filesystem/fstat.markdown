# fstat

The PHP function `fstat` works the same as `stat`, only it takes an open
stream resource as its input instead of a filename.

{{code:php
    $f = fopen('/path/to/foobar', 'r');
    $stat = fstat($f);
    fclose($f)

    print $stat['ino'];
    //=> 16793883
}}

For an open file in Ruby, you can call the `File#stat` instance method.

{{code:ruby
    f = File.open('/path/to/foobar', 'r')
    stat = f.stat
    f.close

    p stat.ino
    #=> 16793883
}}


{{related:
    filesystem/stat
}}
