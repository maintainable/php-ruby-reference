# create_function

Creating lambda style anonymous methods in Ruby is very convenient with the
help of Ruby blocks. We create an anonymous method in Ruby by passing a block
to the `Kernel#lamda` method. This will result in a `Proc` object instance.
While PHP's `create_function` takes strings as arguments, the arguments and
code for an anonymous function in Ruby are specified as block arguments, and
the block body respectively.

We can execute an anonymous method in Ruby using `Proc#call` on our anonymous
method.


{{code:php
    $add = create_function('$num1,$num2', 'return $num1 + $num2;');
    print $add(2, 3);
    // => 5
}}


{{code:ruby
    add = lambda do |num1, num2|
      num1 + num2
    end

    p add.call(2, 3)
    # => 5
}}

