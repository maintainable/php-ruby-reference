# get_object_vars

There are no public object properties of objects in Ruby. Ruby instead uses
public methods as properties. Listing the methods for an object in Ruby is
discussed in [get_class_methods](../classobj/get_class_methods).

In Ruby we can use the `Module#attr_reader` method as a way of easily creating
accessor methods for instance variables within a class. This is vaguely
similar to having a public property.


{{code:php
    class Car {
      public  $doors;
      private $isStarted;
    }
    $vars = get_object_vars(new Car);
    var_export($vars);
    // => array('doors' => NULL)
}}


{{code:ruby
    class Car
      attr_reader :doors

      private
      def started?
        @started
      end
    end
}}


{{related:
    classobj/get_class_methods
    classobj/get_class_vars
}}
