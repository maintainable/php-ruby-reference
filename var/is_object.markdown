# is_object

Interrogating to check if a variable is an object in Ruby is pointless since
everything is an object in Ruby. We can check if something is an object using
`Object#is_a?(Object)`, but this will always return true in Ruby.


{{code:php
    $car = new stdClass;
    $result = is_object($car);
    var_export($result);
    // => true
}}


{{code:ruby
    true.is_a?(Object)    # => true
    'hello'.is_a?(Object) # => true
    1.234.is_a?(Object)   # => true
}}


{{related:
    var/is_bool
    var/is_int
    var/is_float
    var/is_string
    var/is_array
}}
