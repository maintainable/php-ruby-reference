# substr_count

Counting the occurrences of a substring within a string of characters id done
in Ruby using a combination of `String#scan` to scan for the word and
`Array#length` to count the occurrences.

{{code:php
    print substr_count("the cat in the hat", "the");
    // => 2
}}

{{code:ruby
    puts "the cat in the hat".scan("the").length
    # => 2
}}


{{related:
    strings/count_chars
    strings/strpos
    strings/substr
    strings/strstr
}}
