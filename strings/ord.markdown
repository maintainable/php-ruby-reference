# ord

We can find the ASCII value of a character in Ruby using the `String#[]`
method. We use this method in Ruby to specify the index of the character we
need.

{{code:php
    $result = ord("t");
    var_export($result);
    // => 116
}}

{{code:ruby
    p "t"[0]
    # => 116
}}


{{related:
    strings/chr
}}
