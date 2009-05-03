# print

Printing output of a string of characters can be done in a variety of ways in
Ruby. The equivalent of PHP's `print` construct is Ruby's `print` method.

{{code:php
    print "Hello World";
    // => Hello World
}}

{{code:ruby
    print "Hello World"
    # => Hello World
}}

Ruby also has the `puts` method, which will append a newline to the output.

{{code:php
    print "Hello World\n";
    // => Hello World
}}

{{code:ruby
    puts "Hello World"
    # => Hello World
}}

To inspect the value of a variable in Ruby we can use the `p` method. This is
similar to performing a `var_export` in PHP.

{{code:php
    $myVar = array("hello", "world");
    var_export($myVar);  
    // => array (0 => 'hello', 1 => 'world')
}}

{{code:ruby
    my_var = ["Hello", "world"]
    p my_var
    # => ["Hello", "world"]
}}


{{related:                
    strings/echo            
    strings/printf
}}
