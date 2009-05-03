# is_numeric

We can check if a variable is numeric in Ruby using `Object#is_a?`. 


{{code:php
    $number = 2;
    $result = is_numeric($number);
    var_export($result);
    // => true

    $number = 1.2;
    $result = is_numeric($number);
    var_export($result);
    // => true
}}


{{code:php
    number = 2
    p number.is_a?(Numeric)
    # => true

    number = 1.2
    p number.is_a?(Numeric)
    # => true
}}


{{related:
    ctype/ctype_digit
    var/is_bool
    var/is_null
    var/is_float
    var/is_int
    var/is_string
    var/is_object
    var/is_array
}}
