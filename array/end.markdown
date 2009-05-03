# end

Ruby has no internal pointer in array objects like PHP. Because of this, there
is no direct equivalent to PHP's `end` function.

Sometimes `end` is used to grab the last value of an array. We can
do this in Ruby using the `Array#last` method.

{{code:php
    $fruit = array('apple', 'orange');
    $result = end($fruit);
    var_export($result);
    // => 'orange'
}}

{{code:ruby
    fruit = ["apple", "orange"]
    result = fruit.last
    # => "orange"
}}

The `last` method does not work for associative key/value hashes in Ruby since
hashes are unordered collections.


{{related:
    array/current
    array/each
    array/prev
    array/next                
    array/reset
}}
