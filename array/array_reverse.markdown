# array_reverse

We can reverse an array in Ruby using the `Array#reverse` method.

{{code:php
    $fruit = array('apple', 'banana', 'kiwi');
    $result = array_reverse($fruit);
    var_export($result);
    // => array(0 => 'kiwi', 1 => 'banana', 2 => 'apple')
}}

{{code:ruby
    fruit = ["apple", "banana", "kiwi"]
    p fruit.reverse
    # => ["kiwi", "banana", "apple"]
}}


{{related:
    array/array_flip
}}
