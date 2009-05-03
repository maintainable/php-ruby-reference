# array_values

{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}     

To get the values of a hash in Ruby, we can use the `Hash#values` method.

{{code:php
    $dinner = array('fruit' => 'apple', 'meat' => 'chicken');
    $result = array_values($dinner);
    var_export($result);
    // => array(0 => 'apple', 1 => 'chicken')
}}

{{code:ruby
    dinner = {:fruit => "apple", :meat => "chicken"}
    p dinner.values
    # => ["apple", "chicken"]
}}


{{related:
    array/array_keys  
}}
