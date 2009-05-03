# str_shuffle

There is no native function to shuffle the characters of a string in Ruby, but
this can be accomplished easy enough by performing the following:

1. `String#split` the string on every character
2. `Array#sort_by` the characters at random
3. `Array#join` the characters back into a single string
                                                        
{{code:php
    $result = str_shuffle('Hello');
    var_export($result);
    // => 'llHoe'
}}

{{code:ruby
    p "Hello".split("").sort_by { rand }.join
    # => "loHle"
}}


{{related:
    array/shuffle
    math/rand
}}
