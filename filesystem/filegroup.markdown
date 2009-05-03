# filegroup

{{notice:
    This function's solution assumes a Unix-like operating system.
}}

The `filegroup` function in PHP returns the group ID owning a file.

{{code:php
    $gid = filegroup('/path/to/foobar');
    print $gid;

    //=> 501
}}

You can retrieve a file's group ID in Ruby by calling `File.stat`. It will
return a `File::Stat` instance that contains a `gid` attribute.

{{code:ruby
    stat = File.stat('/path/to/foobar')
    p stat.gid

    #=> 501
}}

## Resolving the Group Name

If you also need the name from the group ID, you can use PHP's
`posix_getgrgid` function to retrieve this information and more.

{{code:php
    $gid = filegroup('/path/to/foobar');
    $info = posix_getgrgid($gid);
    print $info['name'];

    //=> "herbert"
}}

The `Etc` module from the Ruby Standard Library provides a `getgrgid` method.
It returns a `Struct` with attributes similar to the keys of the associative
array returned by PHP's `posix_getgrgid`.

{{code:ruby
    require 'etc'

    gid = File.stat('/path/to/foobar').gid
    info = Etc.getgrgid(gid)
    p info.name

    #=> "herbert"
}}

## Comparing to the Current Process

Ruby's `File` class provides an additional method, `grpowned?`, that tests if
the effective group ID of the current process is the group ID of a file.

{{code:ruby
    File.grpowned?('/path/to/foobar')

    #=> true
}}


{{related:
    filesystem/stat
}}
