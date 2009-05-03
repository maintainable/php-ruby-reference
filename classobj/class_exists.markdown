# class_exists

Classes in Ruby are reference by a constant (a variable beginning with an
uppercase letter). We can check if a class is defined by verifying that the
constant exists for the class name using `Module.const_defined?`.


{{code:php
    class Car {}
    $exists = class_exists('Car');
    var_export($exists);
    // => true
}}


{{code:ruby
    class Car; end
    p Module.const_defined?("Car")
    # => true
}}


{{related:
    funchand/function_exists
    classobj/interface_exists
    classobj/get_declared_classes
}}
