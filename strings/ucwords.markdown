# ucwords

Ruby does not have a built-in method to capitalize all of the words within a
string. We can accomplish this using the following example:

1. `String#split` the string into individual words
2. `Enumerable#select` to iterate through the words
3. `String#capitalize!` each word
4. `Array#join` the words back into a single string

{{code:php
    print ucwords("hello world");
    // => Hello World
}}

{{code:ruby
    "hello world".split(' ').select {|w| w.capitalize! || w }.join(' ')
    # => Hello World
}}

Rails includes a built in `String#titleize` method as part of `ActiveSupport`
library. This will perform the equivalent of the above Ruby.

{{code:rails
    "hello world".titleize
    # => Hello World
}}


{{related:
    strings/strtoupper
    strings/strtolower
    strings/ucfirst
}}
