# strpos

To find the position of a substring within a string of characters, we can use
Ruby's `String#index` method.

{{code:php
    print strpos("hello world", "wo");
    // => 6
}}

{{code:ruby
    p "hello world".index("wo")
    # => 6
}}

The `strpos` function is often used to simply check for the presence of a
substring within a string. This is usage is accomplished in Ruby by using the
`String#include?` method.

{{code:php
    $result = (strpos("hello world", "wo") !== false);
    var_export($result);
    // => true
}}

{{code:ruby
    puts "hello world".include?("wo")
    # => true
}}


{{related:
    strings/strrpos
    strings/substr
    strings/strstr
    strings/stripos
    strings/strripos
    strings/strrchr
    strings/stristr
}}
