# array_product

We can get the product of an array of integers using a combination of Ruby's
`Enumerable#inject` method with `Fixnum#*`.

{{code:php
    $numbers = array(2, 2, 2, 2);
    $result = array_product($numbers);
    print $result;
    // => 16
}}

{{code:ruby
    result = [2, 2, 2, 2].inject {|product, element| product * element }
    puts result
    # => 16
}}


{{related:
    array/array_sum
}}
