# base64_decode

In Ruby, we use the `Base64` class to decode data using a base 64
representation. We first need to require the `Base64` library using
`require "base64"`. This is similar to using `require_once` to 
include a class file in PHP.

To get the equivalent result of PHP's `base64_decode` function,
we'll use the `Base64.decode64` class method.


{{code:php
    $result = base64_decode('SGVsbG8gd29ybGQ=');
    var_export($result);
    // => 'Hello world'
}}


{{code:ruby
    require 'base64'

    p Base64.decode64("SGVsbG8gd29ybGQ=")
    # => "Hello world"
}}


{{related:
    url/base64_encode
}}
