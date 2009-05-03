# fileowner

{{notice:
    This function's solution assumes a Unix-like operating system.
}}

The `fileowner` function in PHP returns the user ID owning a file.

{{code:php
    $uid = fileowner('/path/to/foobar');
    print $uid;

    //=> 501
}}

You can retrieve the file owner in Ruby by calling `File.stat`. It will return
a `File::Stat` instance that contains a `uid` attribute.

{{code:ruby
    stat = File.stat('/path/to/foobar')
    p stat.uid

    #=> 501
}}

## Resolving the User Name

If you also need the name from the user ID, you can use PHP's `posix_getpwuid`
function to retrieve this information and more.

{{code:php
    $uid = fileowner('/path/to/foobar');
    $info = posix_getpwuid($uid);
    print $info['name'];

    //=> "herbert"
}}

The `Etc` module from the Ruby Standard Library provides a `getpwuid` method.
It returns a `Struct` with attributes similar to the keys of the associative
array returned by PHP's `posix_getpwuid`.

{{code:ruby
    require 'etc'

    uid = File.stat('/path/to/foobar').uid
    info = Etc.getpwuid(uid)
    p info.name

    #=> "herbert"
}}

## Comparing to the Current Process

Ruby's `File` class provides an additional method, `owned?`, that tests if the
effective user ID of the current process is the user ID of a file.

{{code:ruby
    File.owned?('/path/to/foobar')

    #=> true
}}


{{related:                
    filesystem/stat
}}
