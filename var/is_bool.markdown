# is_bool

We can check if a variable is a boolean in Ruby using `Object#is_a?`.


{{code:php
    $myVar = true;
    $result = is_bool($myVar);
    var_export($result);
    // => true
}}


{{code:ruby
    my_var = true
    p my_var.is_a?(TrueClass) || my_var.is_a?(FalseClass)
    # => true
}}


{{related:
    var/is_float
    var/is_int
    var/is_string
    var/is_object
    var/is_array
}}
