# is_null

We can check if a variable is `null` (`nil` in Ruby) using `Object#is_a?`.


{{code:php
    $value = null;
    $result = is_null($value);
    var_export($result);
    // => true
}}


{{code:php
    value = nil
    p value.nil?
    # => true
}}


{{related:
    var/isset
    var/is_bool
    var/is_numeric
    var/is_float
    var/is_int
    var/is_string
    var/is_object
    var/is_array
}}
