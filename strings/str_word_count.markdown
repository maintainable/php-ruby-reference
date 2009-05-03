# str_word

There is no native way to count the number of words in a Ruby string. Instead
we would use the `String#scan` method to split a string based on a regular
expressionw word boundary, and find the length of the results.

{{code:php
    print str_word_count("hello world");
    // => 2
}}

{{code:ruby
    puts "hello world".scan(/\w+/).length
    # => 2
}}


{{related:
    strings/explode
    pcre/preg_split
    strings/count_chars
    strings/substr_count
    regex/split
}}
