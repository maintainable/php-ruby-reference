# shuffle

We can shuffle an array in Ruby using a combination of `Enumberable#sort_by`
and `Kernel#rand`. It is important to note that the original array is modified
by PHP's `shuffle` function, but is not modified in the Ruby version.

{{code:php
    $fruit = array('apple', 'banana', 'kiwi', 'lime');
    shuffle($fruit);
    var_export($fruit);
    // array(0 => 'kiwi', 1 => 'banana', 2 => 'lime', 3 => 'apple')
}}

{{code:ruby
    fruit = ["apple", "banana", "kiwi", "lime"]
    result fruit.sort_by { rand }
    p result
    # => ["lime", "kiwi", "apple", "banana"]
}}


{{related:
    array/arsort
    array/asort
    array/ksort
    array/rsort
    array/sort 
    array/usort
}}
