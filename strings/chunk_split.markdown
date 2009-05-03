# chunk_split

Splitting a long string into smaller chunks can be done in Ruby using a
sequence of:

1. `String#scan` the string into the specified chunk size
2. `Array#join` the string back together using the ending sequence as the glue
3. `String#+` appends the final ending sequence to the result

{{code:php
    $result = chunk_split("a really long string", 5, "\r\n");
    var_export($result);
    // => "a rea\r\nlly l\r\nong s\r\ntring\r\n"
}}

{{code:ruby
    p "a really long string".scan(/.{1,5}/).join("\r\n") + "\r\n"
    # => "a rea\r\nlly l\r\nong s\r\ntring\r\n"
}}


{{related:                
    strings/str_split     
    strings/explode
    regex/split
    strings/wordwrap
}}
