# in_array

We can check if an element exists in a Ruby array using `Array#include?`.

PHP's `in_array` has a `strict` argument that will consider object type. Ruby
does not consider a Fixnum of `1` and a String of `'1'` to be the same thing,
and will always operate in the equivalent of PHP's `strict = true` argument
for this function.

{{code:php
    $fruit = array('apple', 'banana', 'kiwi');
    $result = in_array('apple', $fruit, true);
    var_export($result);
    // => true
}}

{{code:ruby
    fruit = ["apple", "banana", "kiwi"]
    p fruit.include?("apple")
    # => true
}}

Just like PHP, Ruby can check for an element's existence in an array even if
that element is an array (or any object).

{{code:php
    $list = array(array('a', 'b'), 'c');
    $result = in_array(array('a', 'b'), $list);
    var_export($result);
    // => true
}}

{{code:ruby
    list = [["a", "b"], "c"]
    p list.include?(["a", "b"])
    # => true
}}


{{related:
    array/array_search 
    array/array_key_exists
}}
