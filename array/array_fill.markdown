# array_fill

The `array_fill` function does not translate very well over to Ruby since Ruby
arrays are structured a little differently than PHP's. Arrays in Ruby are a
simple stack of elements, and the key is determined solely by each element's
position in the stack. Because of this, we cannot fill an array starting at a
specific position in the array without filling elements before that position
with something.

The closest we can get to doing something like this is to fill in these
initial positions with a specified number of `nil` elements. It is
however rare that you'll need to do this type of operation in Ruby.

{{code:php
    $result = array_fill(2, 3, 'cat');
    var_export($result);
    // => array(2 => 'cat', 3 => 'cat', 4 => 'cat')
}}

{{code:ruby
    result = [nil] * 2 + ['cat'] * 3
    p result
    # => [nil, nil, 'cat', 'cat', 'cat']
}}


{{related:
  strings/str_repeat
  range
}}
