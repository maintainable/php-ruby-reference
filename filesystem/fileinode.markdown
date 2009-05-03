# fileinode

{{code:php
    $inode = fileinode('/path/to/foobar');
    print $inode;

    //=> 16793883
}}

{{code:ruby
    stat = File.stat('/path/to/foobar')
    p stat.ino

    #=> 16793883
}}


{{related:
    filesystem/stat
}}
