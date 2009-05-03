# array_change_key_case
         
{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby
    arrays don't use associative key/value pairs. See [Array](../array)
    for more details.
}}  


The default `array_change_key_case` behavior is to lowercase all of the keys
in the array. In Ruby we use a combination of `Hash#inject` and
`String#downcase` to achieve the same result.


{{code:php
    $array = array('cHaiRS' => 4, 'tAbLes' => 1);

    $result = array_change_key_case($array, CASE_LOWER);
    var_export($result);
    // => array('chairs' => 4, 'tables' => 1);
}}


{{code:ruby
    hash = {'cHaiRS' => 4, 'tAbLes' => 1}

    result = hash.inject({}) do |hash, keys|
      hash[keys[0].downcase] = keys[1]
      hash
    end
    p result
    # => {"chairs"=>4, "tables"=>1}<a href="array_change_key_case.html" id="" title="array_change_key_case">array_change_key_case</a>
}}


Similarly, we can convert all of keys to uppercase using a combination of
`Hash#inject` and `String#upcase`.


{{code:php
    $array = array('cHaiRS' => 4, 'tAbLes' => 1);

    $result = array_change_key_case($array, CASE_UPPER);
    var_export($result);
    // => array('CHAIRS' => 4, 'TABLES' => 1);
}}


{{code:ruby
    hash = {'cHaiRS' => 4, 'tAbLes' => 1}

    # upper
    result = hash.inject({}) do |hash, keys|
      hash[keys[0].upcase] = keys[1]
      hash
    end
    p result
    # => {"CHAIRS"=>4, "TABLES"=>1}
}}
