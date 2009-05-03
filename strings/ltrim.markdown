# ltrim

Stripping whitespace from the beginning of a string is done in Ruby using the
`String#lstrip` method.

{{code:php
    $result = ltrim(" \nhello world");
    var_export($result);
    // => 'hello world'
}}

{{code:ruby
    p " \nhello world".lstrip
    # => "hello world"
}}

PHP's `ltrim` function has a second argument to specify the characters to
strip. We can do this in Ruby using the `String#gsub` method.

{{code:php
    $result = ltrim(" /Users/joe/work/", "/ ");
    var_export($result);
    // => 'Users/joe/work/'
}}

{{code:ruby
    chars = "/ "
    p " /Users/joe/work/".gsub(/^[#{chars}]+/, '')
    # => "Users/joe/work/"
}}


{{related:
    strings/trim              
    strings/rtrim
}}
