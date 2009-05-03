# method_exists

Calling a method in Ruby is often referred to as "sending a message" to an
object. Ruby methods reflect this idea and terminology. We check if a method
exist by checking if an object "responds to" a certain message using
`Object#respond_to?`.


{{code:php
    class Car {
      public function drive() {}
    }
    $car = new Car;
    $exists = method_exists($car, 'drive');
    var_export($exists);
    // => true
}}


{{code:ruby
    class Car
      def drive; end
    end

    car = Car.new
    p respond_to?(:drive)
    # => true
}}


{{related:
    classobj/function_exists
    classobj/is_callable
}}
