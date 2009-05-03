# is_subclass_of

We can check if an object in Ruby is a subclass of another object using the
`Object.kind_of?` method.


{{code:php
    class Dinosaur {}
    class TRex extends Dinosaur {}

    $t = new TRex;
    $result = is_subclass_of($t, "Dinosaur");
    var_export($result);
    // => true
}}


{{code:ruby
    class Dinosaur; end
    class TRex < Dinosaur; end

    t = TRex.new
    p t.kind_of?(Dinosaur)
    # => true
}}


{{related:
    classobj/get_class
    classobj/get_parent_class
    classobj/is_a
}}
