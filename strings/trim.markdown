# trim

Stripping whitespace from the beginning and end of a string is done in Ruby
using the `String#strip` method.

{{code:php
    $result = trim(" \nhello world \n");
    var_export($result);
    // => 'hello world'
}}

{{code:ruby
    p " \nhello world \n".strip
    # => "hello world"
}}

PHP's `trim` function has a second argument to specify the characters to
strip. We can do this in Ruby using the `String#gsub` method.

{{code:php
    $result = trim(" /Users/joe/work/ ", " /");
    var_export($result);
    // => 'Users/joe/work'
}}

{{code:ruby
    chars = " /"
    p " /Users/joe/work/ ".gsub(/^[#{chars}]+|[#{chars}]+$/, '')
    # => "Users/joe/work"
}}


{{related:                
    strings/ltrim           
    strings/rtrim
}}
