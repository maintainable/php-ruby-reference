# base64_encode

In Ruby, we use the `Base64` class to encode data using a base 64
representation. We first need to require the `Base64` library using `require
"base64"`. This is similar to using `require_once` to include a class file in
PHP.

To get the equivalent result of PHP's `base64_encode` function, we'll use the
`Base64.encode64` class method.


{{code:php
    $result = base64_encode('Hello world');
    var_export($result);
    // => 'SGVsbG8gd29ybGQ='
}}


{{code:ruby
    require 'base64'

    p Base64.encode64("Hello world")
    # => "SGVsbG8gd29ybGQ=\n"
}}


Take note that the Ruby version inserts a newline at the end of the string
where PHP does not.
                   

{{related:
    url/base64_decode 
    strings/chunk_split
    strings/uuencode
}}
