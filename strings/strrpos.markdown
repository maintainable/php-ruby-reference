# strrpos

To find the position of the last occurrence of asubstring within a string of
characters, we can use Ruby's `String#rindex` method.

{{code:php
    print strrpos("hello world", "o");
    // => 7
}}

{{code:ruby
    p "hello world".rindex("o").
    # => 7
}}


{{related:
    strings/strpos
    strings/substr
    strings/strstr
    strings/strripos
    strings/strrchr
    strings/stristr
}}
