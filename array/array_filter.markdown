# array_filter

{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}

Ruby has a real nice way of executing something similar to PHP's
`array_filter` function. In Ruby we don't need to create a callback function
to execute since we can pass this directly into our method with a block.

There are two different ways of getting the equivalent of `array_filter` in
Ruby. One for arrays and one for hashes. To perform the equivalent of an
`array_filter` function on an array we use the `Enumerable#select` method
along with a block which represents the callback function we used in PHP.

{{code:php
    function short($var) {
       return strlen($var) < 5;
    }

    $colors = array('orange', 'purple', 'red', 'blue');
    $result = array_filter($colors, 'short');
    var_export($result);
    // => array(2 => 'red', 3 => 'blue')
}}

{{code:ruby
    colors = ['orange', 'purple', 'red', 'blue']
    p colors.select {|c| c.length < 5 }
    # => ["red", "blue"]
}}

Performing a filter on collection with associative keys is similar, and we
also use `Enumerable#select`. The result of this method is a little different.
Since a hash is not an ordered collection, Ruby returns our results as a
nested array instead of key value pairs. We can cast this back to a hash by
flattening the results and using `Hash.[]` to create a hash out of the values.

{{code:php
    function short($var) {
       return strlen($var) < 5;
    }
    $colors = array('a' => 'orange', 'b' => 'blue', 'c' => 'red');
    $result = array_filter($colors, 'short');
    var_export($result);
    // => array('b' => 'blue', 'c' => 'red')
}}

{{code:ruby
    colors = {:a => 'orange', :b => 'blue', :c => 'red'}
    result = colors.select {|key, value| value.length < 5 }
    result = Hash[*result.flatten]
    # => {:b=>"blue", :c=>"red"}
}}


{{related:
    array/array_map           
    array/array_reduce     
    array/array_walk
}}
