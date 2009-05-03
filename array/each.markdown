# each

Ruby has no internal pointer in array objects like PHP. Because of this, there
is no direct equivalent to PHP's `each` function.

Sometimes the `each` function is used in combination with `list` to iterate
over a list of items.

{{code:php
    $person = array('name' => 'Walter', 'age' => 25);
    while (list($key, $value) = each($person)) {
        print "$key = $value\n";
    }
    // => name = Walter
    //    age = 25
}}

We can do this type of iteration with hash values in Ruby using the hash's
`each` method:
              
{{code:ruby
    person = {:name => "Walter", :age => 25}
    person.each do |key, value| 
      puts "#{key} = #{value}"
    end
    # => name = Walter
    #    age = 25
}}


{{related:
    array/key
    array/list
    array/current
    array/reset
    array/next
    array/prev
}}
