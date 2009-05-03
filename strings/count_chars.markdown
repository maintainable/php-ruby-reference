# count_chars

There is no direct equivalent to count information about characters within a
string, but we can achieve similar results using:

1. `String#split` the string on each character
2. `Array#inject` to build a hash based on the occurrence of characters

{{code:php
    $result = count_chars("test", 1);
    var_export($result);
    // => array(101 => 1, 115 => 1, 116 => 2)
}}

{{code:ruby
    # direct equivalent
    result = "test".split("").inject({}) do |hash, val|
      hash[val[0]] = hash[val[0]].to_i + 1
      hash
    end
    p result
    # => {115=>1, 116=>2, 101=>1}
}}

If all we need is know how many times a specific character occurs within the
string:

{{code:php
    $chars = count_chars("hello world", 1); 
    print $chars[ord('l')];
    // => 3
}}

{{code:ruby
    # number of times a single char occurs
    puts "hello world".scan("l").length
    # => 3
}}


{{related:
    strings/strpos
    strings/substr_count
}}
