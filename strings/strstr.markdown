# strstr

We can find the first occurrence of a string in Ruby by using the
`String#match` method. This will return a `MatchData` object which we can
inspect to retrieve more information about the matched characters.

{{code:php
    print strstr("name@example.com", "@");
    // => @example.com
}}

{{code:ruby
    match = "name@example.com".match('@')
    puts match[0] + match.post_match
    # => @example.com
}}

The `strstr` function is often used to simply check for the presence of a
substring within a string. This is usage is accomplished in Ruby by using the
`String#include?` method.

{{code:php
    $result = (strstr("name@example.com", "@") !== false);
    var_export($result);
    // => true
}}

{{code:php
    puts "name@example.com".include?("@")
    # => true
}}


{{related:
    pcre/preg_match
    strings/strpos
    strings/substr
    strings/stristr
    strings/strrchr
}}
