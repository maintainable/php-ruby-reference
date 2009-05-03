# is_string

We can check if a variable is a string in Ruby using `Object#is_a?`. 


{{code:php
    $string = 'Hello world';
    $result = is_string($string);
    var_export($result);
    // => true
}}


{{code:ruby
    string = "Hello world"
    p string.is_a?(String)
    # => true
}}


{{related:
    var/is_float
    var/is_int
    var/is_bool
    var/is_object
    var/is_array
}}
