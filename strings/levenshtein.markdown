# levenshtein

{{notice:
    This function's solution requires the [text
    gem](http://rubyforge.org/projects/text/).
}}

We can calculate Levenshtein distance between two strings in Ruby with the
help of the [text gem](http://rubyforge.org/projects/text/). To install this
gem:

{{code:bash
    $> sudo gem install Text
    Successfully installed Text-1.1.2
    1 gem installed
}}

{{code:php
    $result = levenshtein('hello', 'world');
    var_export($result);
    // => 4
}}

{{code:ruby
    require 'rubygems'
    require 'text'

    p Text::Levenshtein.distance('hello', 'world')
    # => 4
}}

{{related:
    strings/metaphone
    strings/soundex
}}
