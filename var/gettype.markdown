# gettype

Variables in Ruby don't have a type. Instead they are an instance of an
object. We can interrogate the class of an object instance using
`Object#class`.


{{code:php
    print gettype(true);         // => boolean
    print gettype(1);            // => integer
    print gettype(1.2);          // => double
    print gettype('hello');      // => string
    print gettype(new stdClass); // => object
    print gettype(null);         // => NULL
}}


{{code:ruby
    true.class       # => TrueClass
    1.class          # => Fixnum
    1.2.class        # => Float
    "hello".class    # String
    Object.new.class # Object
    nil.class        # NilClass
}}


{{related:
    var/settype
    var/is_array
    var/is_bool
    var/is_float
    var/is_int
    var/is_null
    var/is_numeric
    var/is_object
    var/is_resource
    var/is_scalar
    var/is_string
    funchand/function_exists
    classobj/method_exists
}}
