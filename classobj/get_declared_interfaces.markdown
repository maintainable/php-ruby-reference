# get_declared_interfaces

There are no interfaces in Ruby the way there is in PHP. Ruby uses class
inheritance or module mixins to specify an interface for an object. Both class
and module names are constants. We can get the list of all classes and modules
by viewing the all defined constants using `Module.constants`.


{{code:php
    $result = get_declared_interfaces();
    var_export($result);
    // => array(0 => 'Traversable', 1 => 'IteratorAggregate', ...)
}}


{{code:ruby
    p Module.constants
    # => ["TrueClass", "ObjectSpace", ...]
}}


{{related:
    classobj/get_declared_classes
    classobj/class_implements    
}}
