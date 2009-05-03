# list

We can do the equivalent of PHP's `list` function in Ruby using parallel
assignment. In Ruby we can assign comma separated variables to elements of an
array using the normal assignment operator.

{{code:php
    $attributes = array('Joe', 25, 'blonde');
    list($name, $age, $hair) = $attributes;
    print $name; // => 'Joe'
    print $age;  // => 25
    print $hair; // => 'blonde'
}}

{{code:ruby
    attributes = ["Joe", 25, "blonde"]
    name, age, hair = attributes
    puts name # => "Joe"
    puts age  # => 25
    puts hair # => "blonde"
}}


{{related:
    array/each 
    array/array 
    array/extract
}}
