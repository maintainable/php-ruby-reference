# is_a

We can check if an object instance is of a certain class in Ruby using the
`Object.is_a?` method.


{{code:php
    class Car {}
  
    $bmw = new Car;
    $result = is_a($bmw, "Car");
    var_export($result);
    // => true
}}


{{code:ruby
    class Car; end

    bmw = Car.new
    p bmw.is_a?(Car)
    # => true
}}


{{related:
    classobj/get_class
    classobj/get_parent_class
    classobj/is_subclass_of
}}
