# get_class_methods

In PHP, `get_class_methods` is used in two different ways. The first way is to
pass in a class name string to get the methods. We can get a list of the
public instance methods defined on a class in Ruby using
`Object.instance_methods`.

                         
{{code:php
    class Car {
        public function drive() {}
        private function brake() {}
    }

    $result = get_class_methods('Car');
    var_export($result);
    // => array (0 => 'drive')
}}


{{code:ruby
    class Car
      def drive; end
  
      private
      def brake; end
    end

    p Car.instance_methods
    # => ["inspect", "clone", "method", ...]
}}


The other way is to pass in an object instance of the class to get the
methods. We can get a list of methods for an object in Ruby using
`Object#methods`.


{{code:php
    $result = get_class_methods(new Car);
    var_export($result);
    // => array (1 => 'drive')
}}


{{code:ruby
    p Car.new.methods
    # => ["inspect", "clone", "method", ...]     
}}


In Ruby, all objects instances inherit from the a base `Object`, so we get a
rather long list of methods -- including our user defined methods.

If we want to only see a list of user defined public methods, we can use the
`Enumerable#reject` method to exclude all of the methods inherited from
Object.


{{code:ruby
    p Car.new.methods.reject {|m| Object.methods.include?(m) }
    # => ["drive"]
}}


{{related:
    classobj/get_class
    classobj/get_class_vars
    classobj/get_object_vars
}}
