# metaphone

{{notice:
    This function's solution requires the [text
    gem](http://rubyforge.org/projects/text/).
}}

We can calculate the `metaphone` key of a string in Ruby with the help of the
[text gem](http://rubyforge.org/projects/text/). To install this gem:

{{code:bash
    $> sudo gem install Text
    Successfully installed Text-1.1.2
    1 gem installed
}}

Once this gem is installed, we can calculate the `metaphone` using:

{{code:php
    $result = metaphone("hello world");
    var_export($result);
    // => 'HLWRLT'
}}

To get the equivalent of the string in PHP, we need to first strip whitespace
from the string.

{{code:ruby
    require 'rubygems'
    require 'text'

    text = "hello world".gsub(/\s/, '')
    p Text::Metaphone.metaphone(text)
    # => "HLWRLT"
}}


{{related:
    strings/levenshtein
    strings/soundex
    strings/similar_text
}}
