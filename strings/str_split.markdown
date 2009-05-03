# str_split

Converting a string into an array of separate chunks is done in Ruby using the
`String#scan` method along with the regular expression shown below.

{{code:php
    $result = str_split("Hello World", 3);
    var_export($result);
    // => array(0 => 'Hel', 1 => 'lo ', 2 => 'Wor', 3 => 'ld')
}}

{{code:ruby
    p "Hello World".scan(/.{1,3}/)
    # => ["Hel", "lo ", "Wor", "ld"]
}}

To change the chunk size, we adjust the regular expression accordingly.
Splitting into 20 character chunks would require the regular expression:
`/.{1,20}/`


{{related:
    strings/chunk_split
    pcre/preg_split
    strings/explode
    strings/count_chars
    strings/str_word_count
}}
