# get_class

To get the class name of an object in Ruby, we use the `Object#class` method.
The `class` method in Ruby returns a constant which references the class
object. To get a string representation of this class name, we must use `to_s`
on the result.


{{code:php
    class Car {}
    $bmw = new Car;
    $result = get_class($bmw);
    var_export($result);
    // => 'Car'
}}


{{code:ruby
    class Car; end
    bmw = Car.new
    p bmw.class.to_s
    # => "Car"
}}


{{related:                
    classobj/get_parent_class
    var/gettype
    classobj/is_subclass_of
}}
