# get_parent_class

We can get the parent class for an object in Ruby by first referencing the
class object using the `Object#class`. Once we have the class object, we
can use the `Class#superclass` method to find the superclass.


{{code:php        
    class Dinosaur {}
    class TRex extends Dinosaur {}

    $t = new TRex;
    $result = get_parent_class($t);
    var_export($result);
    // => 'Dinosaur'
}}


{{code:ruby
    class Dinosaur; end
    class TRex < Dinosaur; end

    t = TRex.new
    p t.class.superclass
    # => Dinosaur
}}


{{related:
    classobj/get_class
    classobj/is_subclass_of
}}
