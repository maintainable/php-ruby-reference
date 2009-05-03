# array_push

We can push additional elements to the end of an array in Ruby using the
`Array#push` method.

{{code:php
    $fruit = array('apple', 'banana');
    array_push($fruit, 'kiwi', 'lime');
    var_export($fruit);
    // => array(0 => 'apple', 1 => 'banana', 2 => 'kiwi', 3 => 'lime')
}}

{{code:ruby
    fruit = ["apple", "banana"]
    fruit.push("kiwi", "lime")
    # => ["apple", "banana", "kiwi", "lime"]
}}


{{related:
    array/array_pop           
    array/array_shift         
    array/array_unshift
}}
