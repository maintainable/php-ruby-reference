# crc32

To calculate the crc32 polynomial of a string, Ruby uses the `Zlib` library's
`Zlib.crc32` class method.

{{code:php
    $result = crc32("hello world");
    var_export($result);
    // => 222957957
}}

{{code:ruby
    require 'zlib'

    p Zlib.crc32("hello world")
    # => 222957957
}}


{{related:
    strings/md5
    strings/sha1
}}
