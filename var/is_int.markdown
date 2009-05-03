# is_int

We can check if a variable is an integer in Ruby using `Object#is_a?`.


{{code:php
    $number = 2;
    $result = is_float($number);
    var_export($result);
    // => true
}}


{{code:php
    number = 2
    p number.is_a?(Integer)
    # => true
}}


{{related:
    var/is_bool
    var/is_float
    var/is_numeric
    var/is_string
    var/is_array
    var/is_object
}}
