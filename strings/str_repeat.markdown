# str_repeat

Repeating a string in Ruby uses the multiplication operator -- the `String#*`
method.

{{code:php
    $result = str_repeat("abc", 5);
    var_export($result); 
    // => 'abcabcabcabcabc'
}}

{{code:ruby
    result = "abc" * 5
    p result
    # => "abcabcabcabcabc"
}}


{{related:
    strings/str_pad
    strings/substr_count
}}
