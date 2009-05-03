# count

We can count the number of elements in an array in Ruby using the
`Array#length` method.

{{code:php
    $numbers = array(1, 2, 3);
    print count($numbers);
    // => 3
}}

{{code:ruby
    numbers = [1, 2, 3]
    puts numbers.length
    # => 3
}}

An important gotcha to remember is that while we can skip elements in an array
in PHP, we cannot do so in Ruby. If you add a tenth element to an array, Ruby
will fill in the missing elements with `nil`.

{{code:php
    $numbers = array(1, 2);
    $numbers[10] = 3;
    print count($numbers);
    // => 3
}}

{{code:ruby
    numbers = [1, 2]
    numbers[10] = 3
    puts numbers.length
    # => 11
}}


{{related:
    var/is_array
    strings/strlen
}}
