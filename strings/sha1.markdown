# sha1

We use the `Digest::SHA1` class to build the equivalent cryptographic hash to
PHP's `sha1` function. This works the same as the `Digest::MD5` class
mentioned in [md5](../strings/md5), and needs to require the `Digest` library 
using `require "digest"`.

{{code:php
    print sha1("my string");
    // => e19343e6c6c76f8f634a685eba7c0880648b1389
}}

{{code:ruby
    require "digest"

    print Digest::SHA1.hexdigest("my string")
    # => e19343e6c6c76f8f634a685eba7c0880648b1389
}}


{{related:
    strings/crc32
    strings/sha1_file
    strings/md5
    strings/md5_file
}}
