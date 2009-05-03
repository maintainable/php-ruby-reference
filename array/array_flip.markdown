# array_flip

{{code:php
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}

We can swap key/values in a Ruby hash using `Hash#invert`. 

{{code:php
    $array = array('bike' => 1, 'car' => 2, 'truck' => 3);
    $result = array_flip($array);
    var_export($result);
    // => array(1 => 'bike', 2 => 'car', 3 => 'truck')
}}

{{code:ruby
    hash = {'bike' => 1, 'car' => 2, 'truck' => 3}
    p hash.invert
    # => {1 => "bike", 2 => "car", 3 => "truck"}
}}

Just like in PHP, conflicting keys will be overwritten. 

{{code:php
    $array = array('bike' => 1, 'car' => 1, 'truck' => 2);
    $result = array_flip($array);
    var_export($result);
    // => array(1 => 'car', 2 => 'truck')
}}

{{code:ruby
    hash = {'bike' => 1, 'car' => 1, 'truck' => 2}
    p hash.invert
    # => {1 => "car", 2 => "truck"}
}}


{{related:
    array/array_values
    array/array_keys
    array/array_reverse
}}
