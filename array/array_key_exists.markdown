# array_key_exists

{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}

To check if a key exists in a Ruby hash, we can use `Hash#include?`.

{{code:php
    $colors = array('orange' => 1, 'yellow' => 4);
    $result = array_key_exists('orange', $colors);
    var_export($result);
    // => true
}}

{{code:ruby
    colors = {:orange => 1, :yellow => 4}  
    p colors.include?(:orange)
    # => true
}}

In PHP, we use `array_key_exists` instead of `isset` when it is important to
know if a key actually exists, and is not just null. `Hash#include?` works
similarly and will return `true` for a key even if it has a `nil` value.

{{code:php
    $colors = array('orange' => 1, 'red' => null);
    $result = isset($colors['red']);
    var_export($result);
    // => false

    $result = array_key_exists('red', $colors);
    var_export($result);
    // => true
}}

{{code:ruby
    colors = {:orange => 1, :red => nil}  
    p colors[:red]
    # => nil

    p colors.include?(:red)
    # => true
}}


{{related:
    array/array_keys          
    array/array
}}
