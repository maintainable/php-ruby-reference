# array_keys
            
{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}

To get the keys of an associative hash in Ruby, we can use the `Hash#keys` method.

{{code:php
    $person = array('name' => 'Walter', 'age' => 25);
    $result = array_keys($person);
    var_export($result);
    // => array(0 => 'name', 1 => 'age')
}}

{{code:ruby
    person = {:name => "Walter", :age => 25}
    p person.keys
    # => [:age, :name]
}}

We can specify a value to match when retrieving keys by adding a second
argument to PHP's `array_keys` function. We can achieve a similar result in
Ruby using a block.

{{code:php
    $fruit = array('apple', 'orange', 'grape', 'apple');
    $result = array_keys($fruit, 'apple');
    var_export($result);
    // => array(0 => 0, 1 => 3)
}}

{{code:ruby
    fruit = ["apple", "orange", "grape", "apple"]

    result = []
    fruit.each_with_index do |value, key| 
      result.push(key) if value == "apple"
    end
    p result
    # => [0, 3]
}}


{{related:
    array/array_values        
    array/array_key_exists
}}
