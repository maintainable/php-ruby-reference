# str_pad

Instead of padding text, Ruby arrives at a similar goal by
justifying text to the left or right. We can left justify (`STR_PAD_RIGHT`)
text using Ruby's `String#ljust` method. Just like PHP's `str_pad` function,
we can specify the final string length along with the character we are using
to pad.

{{code:php
    $result = str_pad("Hello", 10);
    var_export($result);
    // => 'Hello     '

    $result = str_pad("Hello", 10, '-');
    var_export($result);
    // => 'Hello-----'
}}

{{code:ruby
    p "Hello".ljust(10)
    # => "Hello     "

    p "Hello".ljust(10, '-')
    # => "Hello-----"
}}

We can right justify (`STR_PAD_LEFT`) text using a similar approach with
Ruby's `String#rjust` method.

{{code:php
    $result = str_pad("Hello", 10, ' ', STR_PAD_LEFT);
    var_export($result);
    // => '     Hello'
}}

{{code:ruby
    p "Hello".rjust(10)
    # => "     Hello"
}}

Padding on both sides (`STR_PAD_BOTH`) would require us to use both
`String#rjust` and `String#ljust` in combination.

{{code:php
    $result = str_pad("Hello", 10, ' ', STR_PAD_BOTH);
    var_export($result);
    // => '  Hello   '
}}

{{code:ruby
    p "Hello".rjust(7).ljust(10)
    # => "  Hello   "
}}
