# is_float

We can check if a variable is a float in Ruby using `Object#is_a?`. 


{{code:php
    $number = 1.2;
    $result = is_float($number);
    var_export($result);
    // => true
}}


{{code:ruby
    number = 1.2
    p number.is_a?(Float)
    # => true
}}


{{related:
    var/is_bool
    var/is_int
    var/is_numeric
    var/is_string
    var/is_array
    var/is_object
}}
