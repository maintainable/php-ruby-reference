# str_ireplace

All replacements in Ruby are done using `String#gsub`. This method does both
regular expression and string based replacements. To perform case insensitive
replacements in Ruby, we need to use regular expressions with the case
insensitive (`i`) modifier.

{{code:php
    $result = str_ireplace('hello', 'Hi', 'Hello world');
    var_export($result);
    // => 'Hi world'
}}

{{code:ruby
    p "Hello world".gsub(/hello/i, "Hi")
    # => "Hi world"
}}


{{related:
    strings/str_replace
    pcre/preg_replace
    strings/strtr
}}
