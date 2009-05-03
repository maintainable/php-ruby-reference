# md5

In PHP, we use the `md5` function to calculate an MD5 hash. In Ruby, we use
the `Digest::MD5` class. We first need to require the `Digest` library using
`require "digest"`. This is similar to using `require_once` to include a class
in PHP. To get the equivalent of the hash we'd generate using `md5()`, we use
the `hexdigest` method.

{{code:php
    print md5("my string");
    // => 2ba81a47c5512d9e23c435c1f29373cb
}}

{{code:ruby
    require "digest"

    print Digest::MD5.hexdigest("my string")
    # => 2ba81a47c5512d9e23c435c1f29373cb
}}


{{related:
    strings/crc32
    strings/md5_file
    strings/sha1_file
    strings/sha1
}}
