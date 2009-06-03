# array_rand

We can find a random element of an array in Ruby by accessing a random element
of the array with using a combination of the `Array#[]` method with
`Kernel#rand`.

{{code:php
    $fruit = array('apple', 'banana', 'kiwi', 'lime');
    $key   = array_rand($fruit);
    print $fruit[$key]."\n";
    // => 'lime'
}}

{{code:ruby
    fruit = ["apple", "banana", "kiwi", "lime"]
    fruit[rand(fruit.length)]
    # => "lime"
}}

The Rails `ActiveSupport` library provides a simple shortcut method for this
as `Array#rand`.

{{code:rails
    fruit = ["apple", "banana", "kiwi", "lime"]
    fruit.rand
    # => "lime"
}}

{{related:
    array/shuffle
}}
