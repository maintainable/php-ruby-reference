# range

Ruby has the `Range` object for handling a range of integers or strings.
Ranges in Ruby are different than creating a range with PHP's `range` function
in that they are a unique object, and not a shortcut for creating an array. We
create ranges in Ruby using `..` or `...` literal syntax.

We can loop through the range just like we would with an array or hash using
Enumerable methods such as `each`.

{{code:php
    $sequence = range(0, 3);
    var_export($sequence);
    // => array(0 => 0, 1 => 1, 2 => 2, 3 => 3)

    foreach ($sequence as $item) {
        print "$item, ";
    }
    // => 0, 1, 2, 3,
}}

{{code:ruby
    sequence = 0..3
    p sequence
    # => 0..3

    sequence.each {|item| print "#{item}, " } 
    # => 0, 1, 2, 3,
}}

Just like PHP, we can also create an iterable range of sequential strings.

{{code:php
    $alphas = range('a', 'd');
    var_export($alphas);
    // => array(0 => 'a', 1 => 'b', 2 => 'c', 3 => 'd')

    foreach ($alphas as $item) {
        print "$item, ";
    }
    // => a, b, c, d,
}}                   

{{code:ruby
    alphas = 'a'..'d'
    p alphas
    # => "a".."d"

    alphas.each {|item| print "#{item}, " } 
    # => a, b, c, d,
}}

{{related:                
    array/shuffle  
    array/array_fill
}}
