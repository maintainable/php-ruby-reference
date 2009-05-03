# array_count_values
                    
{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}

We can count the occurrences of the values in an array in Ruby using the
`Array#inject` method to build a hash of values.

{{code:php
    $list = array('a', 'cat', 'a', 1, 'cat');
    $result = array_count_values($list);
    var_export($result);
    // => array('a' => 2, 'cat' => 2, 1 => 1)
}}

{{code:ruby
    list = ['a', 'cat', 'a', 1, 'cat']
    result = list.inject({}) do |hash, key|
      hash.include?(key) ? hash[key] += 1 : hash[key] = 1
      hash
    end
    p result
    # => {"cat"=>2, "a"=>2, 1=>1}
}}


{{related:                
    array/count             
    array/array_unique       
    strings/count_chars
}}
