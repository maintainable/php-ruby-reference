# is_array

We can check if a variable is an array in Ruby using `Object#is_a?`.

                           
{{code:php
    $colors = array('red', 'green', 'blue');
    $result = is_array($colors);
    var_export($result);
    // => true
}}


{{code:ruby
    colors = ["red", "green", "blue"]
    p colors.is_a?(Array)
    # => true
}}


{{related:
    var/is_float
    var/is_int
    var/is_string
    var/is_object
}}
