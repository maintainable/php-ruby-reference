# property_exists

There are no public class properties of objects in Ruby. Ruby instead uses
public methods as properties. Checking if a method exists for a class in Ruby
is is discussed in [method_exists](../classobj/method_exists).

In Ruby we can use the `Module#attr_reader` method as a way of easily creating
accessor methods for instance variables within a class. This is vaguely
similar to having a public property.


{{code:php
    class Car {
      public $doors;
    }
    $car = new Car;
    $exists = property_exists($car, 'doors');
    var_export($exists);
    // => true
}}


{{code:ruby
    class Car
      attr_reader :doors
    end

    car = Car.new
    p respond_to?(:doors)
    # => true
}}


{{related:
    classobj/method_exists
}}
