# rtrim

Stripping whitespace from the end of a string is done in Ruby using the
`String#rstrip` method.

{{code:php
    $result = rtrim("hello world \n");
    var_export($result);
    // => 'hello world'
}}

{{code:ruby
    p "hello world \n".rstrip
    # => "hello world"
}}

PHP's `rtrim` function has a second argument to specify the characters to
strip. We can do this in Ruby using the `String#gsub` method.

{{code:php
    $result = rtrim("/Users/joe/work/ ", " /");
    var_export($result);
    // => '/Users/joe/work'
}}

{{code:ruby
    chars = " /"
    p "/Users/joe/work/ ".gsub(/[#{chars}]+$/, '')
    # => "/Users/joe/work"
}}


{{related:
    strings/trim
    strings/ltrim
}}
