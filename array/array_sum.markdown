# array_sum

We can get the sum of an array of integers using a combination of Ruby's
`Enumerable#inject` method with `Fixnum#+`.

{{code:php
    $numbers = array(1, 2, 3);
    $result = array_sum($numbers);
    print $result."\n";
    // => 6
}}

{{code:ruby
    result = [2, 2, 2, 2].inject {|sum, element| sum + element }
    puts result
    # => 6
}}

The `ActiveSupport` library that comes with Rails includes an `Enumerable#sum`
method to simplify this operation.

{{code:rails
    [1, 2, 3].sum
}}

{{related:
    array/array_product  
}}
