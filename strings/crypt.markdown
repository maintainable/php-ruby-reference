# crypt

PHP's `crypt` function returns an encrypted string using a standard Unix
DES-based encryption or an alternate based on the system. This operation has
very similar usage in PHP and Ruby. Ruby uses the `String#crypt` method with a
single salt parameter to get the same result.

{{code:php
    print crypt("my string", "salt");
    // => saGMxKJ.nmUhU
}}

{{code:ruby
    print "my string".crypt("salt")
    # => saGMxKJ.nmUhU
}}


{{related:
    strings/md5
}}
