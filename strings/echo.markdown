# echo

Outputting a string in Ruby is done with the `print` method. Whereas `echo` is
a language construct in PHP, `Kernel#print` is an actual method in Ruby. See
[print](../strings/print) for more information on outputting strings.

{{code:php
    echo "Hello World";
    // => Hello World
}}

{{code:ruby
    print "Hello World"
    # => Hello World
}}


{{related:
    strings/print
    strings/printf
}}
