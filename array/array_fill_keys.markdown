# array_fill_keys

{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby
    arrays don't use associative key/value pairs. See [Array](../array)
    for more details.
}}

There is no direct equivalent of the array_fill_keys method in Ruby. We can
achieve the same results by building a new hash from existing array
information using the `Enumerable#inject` method.

{{code:php
    $keys = array('peel', 'eat');
    $result = array_fill_keys($keys, 'orange');
    var_export($result);
    // => array('peel' => 'orange', 'eat' => 'orange')
}}

{{code:ruby
    keys = ['peel', 'eat']
    result = keys.inject({}) do |hash, key| 
      hash[key] = 'orange'
      hash 
    end
    p result
    # => {"eat"=>"orange", "peel"=>"orange"}
}}


{{related:                   
    array/array_fill        
    array/array_combine
}}
