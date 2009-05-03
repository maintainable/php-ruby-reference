# function_exists

We can check if a method exists in Ruby by seeing if an object responds to a
message by that method's name. We do this using the
`Object#respond_to?` method which takes a single argument using a
symbol of the method we're checking.


{{code:php
    function foo() {}

    $result = function_exists('foo');
    var_export($result);
    // => true

    $result = function_exists('bar');
    var_export($result);
    // => false
}}


{{code:ruby
    def foo; end

    p respond_to?(:foo)
    # => true

    p respond_to?(:bar)
    # => false
}}


{{related:
    classobj/method_exists
    var/is_callable
    funchand/get_defined_functions
}}
