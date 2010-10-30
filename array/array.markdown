# array

There are many ways to create an array in PHP using the `array`
function. It is important to remember that Ruby uses both `Array`
and `Hash` objects to implement the various functionality of PHP
arrays. See [Array](../array) for more details.


## Ordered Arrays

Only numerically indexed arrays are ordered in Ruby. We can create a
numerically indexed array a few different ways. The most popular is using
square brackets with comma separated list. An alternate syntax is to use
`%w{}` to build an array out of a list of words.

Notice that Ruby does not store a numbered index like the PHP array. Ruby
arrays are a simple stack where index is determined by position only. You
cannot skip elements in a Ruby array.


{{code:php
    $array = array('chicago', 'london', 'paris');
    var_export($array);
    // => array(0 => 'chicago', 1 => 'london', 2 => 'paris')
}}


{{code:ruby
    array = ["chicago", "london", "paris"]
    # or
    array = %w{ chicago london paris }

    p array
    # => ["new york", "london", "paris"]
}}


## Associative Arrays

We create associative arrays in Ruby using hashes. The most common syntax to
create a hash in Ruby is using curly braces with a comma separated list of key
value pairs.

In Ruby we'll typically use symbols for the keys of our hashes instead of a
string. Symbols are a lightweight replacement for strings when you simply need
to name something, and don't need a full string object. This tends to be the
case most of the time when we are creating a hash. We simply need a label or
name to use when referring back to a value in the hash.

Remember that hashes are unordered collections. You must use a Ruby array
object if you need an ordered collection.

{{code:php
    $array = array('age' => 26, 'name' => 'Joe', 'country' => 'USA');
    var_export($array);
    // => array('age' => 26, 'name' => 'Joe', 'country' => 'USA')
}}


{{code:ruby
    hash = {:age => 26, :name => "Joe", :country => "USA"}
    p hash
    # => {:name=>"Joe", :age=>26, :country=>"USA"}
}}


## Mixed Arrays

We can create collections with a mix of numeric and string based keys in Ruby
using hashes. PHP automatically assigns a numeric index to elements without a
specified key. Ruby is different in that it requires you to specify the key
value on every element.


{{code:php
    $array = array('age' => 25, 1, 'name' => 'Joe', 2);
    var_export($array);
    // => array('age' => 25, 0 => 1, 'name' => 'Joe', 1 => 2)
}}


{{code:ruby
    hash = {:age => 25, 0 => 1, :name => "Joe", 1 => 2}
    p hash
    # => {0=>1, :age=>25, 1=>2, :name=>"Joe"}
}}


{{related:
    array_pad
    list
    count
    range
}}
