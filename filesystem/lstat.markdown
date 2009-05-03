# lstat

The `lstat` function in PHP returns an associative array with information
about a file or a symbolic link. It is the same as PHP's `stat`, but it does
not follow the last symbolic link. Instead, it reports on the link itself.

{{code:php
    $stat = lstat('/path/to/foobar');
    print $stat['ino'];

    //=> 16793883
}}

Ruby's `File.lstat` method will return a `File::Stat` instance with the same information.

{{code:ruby
    stat = File.lstat('/path/to/foobar')
    p stat.ino

    #=> 16793883
}}


{{related:
    filesystem/stat
}}
