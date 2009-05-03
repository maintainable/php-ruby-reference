# explode

We can split a string by a delimiting string in Ruby using `String#split`.
Ruby uses this same method to perform regular expression based splits. See 
[preg_match](../pcre/preg_match) for examples.

{{code:php
    $result = explode("; ", "derek@example.com; mike@example.com");
    var_export($result);
    // => array(0 => 'derek@example.com', 1 => 'mike@example.com')
}}

{{code:ruby
    p "derek@example.com; mike@example.com".split("; ")
    # => ["derek@example.com", "mike@example.com"]
}}


{{related:
    pcre/preg_split
    strings/str_split
    strings/strtok
    strings/implode
}}
