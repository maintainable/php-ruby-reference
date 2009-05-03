# str_replace

All replacements in Ruby are done using `String#gsub`. This method does both
regular expression and string based replacements.

{{code:php
    $result = str_replace('Hello', 'Hi', 'Hello world');
    var_export($result);
    // => 'Hi world'
}}

{{code:ruby
    p "Hello world".gsub("Hello", "Hi")
    # => "Hi world"
}}

Ruby also has the `String#gsub!` method which modifies the string value
directly.

{{code:ruby
    my_string = "Hello world"

    # the original string remains the same (we use the return value)
    my_string.gsub("Hello", "Hi")
    p my_string
    # => "Hello world"

    # the original string is modified
    my_string.gsub!("Hello", "Hi")
    p my_string
    # => "Hi world"
}}


{{related:
    strings/str_ireplace
    strings/substr_replace
    pcre/preg_replace
    strings/strtr
}}
