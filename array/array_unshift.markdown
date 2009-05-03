# array_unshift

We can unshift elements off of the beginning of an array in Ruby using the
`Array#unshift` method.

{{code:php
    $fruit = array('kiwi', 'lime'); 
    array_unshift($fruit, 'apple', 'orange');
    var_export($fruit);
    // => array(0 => 'apple', 1 => 'orange', 2 => 'kiwi', 3 => 'lime')
}}

{{code:ruby
    fruit = ["kiwi", "lime"]
    fruit.unshift("apple", "orange")
    p fruit
    # => ["apple", "orange", "kiwi", "lime"]
}}


{{related:
    array/array_shift         
    array/array_push          
    array/array_pop
}}
