# stat

We use the `stat` function in PHP to get an associative array with information
about a file:

{{code:php
    $stat = stat('/path/to/foobar');
    print $stat['ino'];

    //=> 16793883
}}

Ruby's `File.stat` method will return a `File::Stat` instance with the same
information.

{{code:ruby
    stat = File.stat('/path/to/foobar')
    p stat.ino

    #=> 16793883
}}


{{related:
    filesystem/lstat 
    filesystem/fstat       
    filesystem/filemtime      
    filesystem/filegroup
}}
