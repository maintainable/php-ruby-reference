# current

Ruby has no internal pointer in array objects like PHP. Because of this, there
is no direct equivalent to PHP's <inlinecode>current</inlinecode> function.

Sometimes `current` is used to grab the first value of an array. We can do
this in Ruby using the `Array#first` method.

{{code:php
    $fruit = array('apple', 'orange');
    $result = current($fruit);
    var_export($result);
    // => 'apple'
}}

{{code:ruby
    fruit = ["apple", "orange"]
    result = fruit.first
    # => "apple"
}}

The `first` method does not work for associative key/value hashes in Ruby
since hashes are unordered collections.


{{related:
    array/end
    array/key
    array/next
    array/prev
    array/each  
}}
