# array_unique

We can find the unique elements of an array in Ruby using `Array#uniq`.

{{code:php
    $fruit = array('apple', 'kiwi', 'apple', 'apple', 'lime');
    $result = array_unique($fruit);
    var_export($result);
    // = array(0 => 'apple', 1 => 'kiwi', 4 => 'lime')
}}

{{code:ruby
    fruit = ["apple", "kiwi", "apple", "apple", "lime"]
    p fruit.uniq
    # => ["apple", "kiwi", "lime"]
}}

One thing to note is that while PHP does not factor data type in to the
uniqueness of the elements, Ruby does. A Fixnum `1` is different than a String
`"1"` in Ruby.

{{code:php
    $input = array(1, 2, '1', '2');
    $result = array_unique($input);
    var_export($result);
    // => array(0 => 1, 1 => 2)
}}

{{code:ruby
    input = [1, 2, "1", "2"]
    p input.uniq
    # => [1, 2, "1", "2"]
}}

We can emulate the PHP behavior by converting the data in the array to a
common type before using the `uniq` method.

{{code:ruby
    input = [1, 2, "1", "2"]
    p input.collect {|val| val.to_s }.uniq
    # => ["1", "2"]
}}
