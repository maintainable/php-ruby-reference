# array_shift

We can shift elements off of the beginning of an array in Ruby using
`Array#shift`.

{{code:php
    $fruit = array('apple', 'banana', 'kiwi');
    $result = array_shift($fruit);
    print $result;
    // => 'apple'

    var_export($fruit);
    // => array(0 => 'banana', 1 => 'kiwi')
}}

{{code:ruby
    fruit = ["apple", "banana", "kiwi"]
    result = fruit.shift
    p result 
    # => "apple"

    p fruit
    # ["banana", "kiwi"]
}}


{{related:
    array/array_unshift       
    array/array_push          
    array/array_pop
}}
