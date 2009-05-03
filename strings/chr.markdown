# chr

We can find a character by it's ASCII value in Ruby using the `Integer#chr`
method.

{{code:php
    $result = chr(116);
    var_export($result);
    // => 't'
}}

{{code:ruby
    p 116.chr
    # => "t"
}}


{{related:
    strings/sprintf
}}
