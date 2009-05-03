# array_pop

We can pop an element off the end of an array in Ruby using the `Array#pop`
method.

{{code:php
    $fruit = array('apple', 'banana', 'kiwi');
    $result = array_pop($fruit);
    var_export($result);
    // => 'kiwi'

    var_export($fruit);
    // => array(0 => 'apple', 1 => 'banana')
}}

{{code:ruby
    fruit = ["apple", "banana", "kiwi"]
    result = fruit.pop
    p result
    # => "kiwi"

    p fruit
    # => ["apple", "banana"]
}}


{{related:
    array/array_push
    array/array_shift
    array/array_unshift
}}
