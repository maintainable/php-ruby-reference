# substr

Retrieving part of a string by a specified position is done in Ruby using
`String#[]` or it's synonym method `String#slice`.

Return the first five characters of a string:

{{code:php
    print substr("hello world", 0, 5);
    // hello
}}

{{code:ruby
    puts "hello world".slice(0, 5)
    puts "hello world"[0, 5]
    # hello
}}

Return all characters after a specified position. In Ruby we can use Ranges to
specify a range of character positions:

{{code:php
    print substr("hello world", 3);
    // lo world
}}

{{code:ruby
    puts "hello world".slice(3..-1)
    puts "hello world"[3..-1]
    # lo world
}}

Return the last five characters in the string:

{{code:php
    print substr("hello world", -5);
    // world
}}

{{code:ruby
    puts "hello world"[-5, 5]
    puts "hello world".slice(-5, 5)
    # world
}}


{{related:
    strings/substr_replace
    pcre/preg_match
    strings/trim
    strings/wordwrap
    strings/strrchr
    strings/mb_substr
}}
