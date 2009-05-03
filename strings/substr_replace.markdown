# substr_replace

We can replace a substring of characters within a string using a similar
method to that demonstrated in Ruby's syntax for [substr](../strings/substr).
This time however we're assigning a new value to positions we specify.

Assign the first five characters of a string:

{{code:php
    print substr_replace("hello world", "hey", 0, 5);
    // => hey world
}}

{{code:ruby
    puts "hello world"[0, 5] = "hey"
    # => hey world
}}

Assign all characters after a specified position. In Ruby we can use Ranges to
specify a range of character positions:

{{code:php
    print substr_replace("hello world", "p", 3);
    // => help
}}

{{code:ruby
    puts "hello world"[3..-1] = "p"
    # => help
}}

Assign the last five characters in the string:

{{code:php
    print substr_replace("hello world", "p", 3);
    // => help
}}

{{code:ruby
    puts "hello world"[3..-1] = "p"
    # => help
}}


{{related:
    strings/str_replace
    strings/substr
}}
