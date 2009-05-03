# interface_exists

There are no interfaces in Ruby the way there is in PHP. Ruby uses class
inheritance or module mixins to specify an interface for an object. Both class
and module names are constants, so we can check if either of these exist by
verifying that the constant exists for the class or module name using
`Module.const_defined?`.


{{code:php
    interface Carnivore {}

    $exists = interface_exists('Carnivore');
    var_export($exists);
    // => true
}}


{{code:ruby
    class Dinosaur; end
    module Carnivore; end

    p Module.const_defined?("Dinosaur")  # => true
    p Module.const_defined?("Carnivore") # => true
}}


{{related:
    classobj/class_exists
}}
