# soundex

{{notice:
    This function's solution requires the [text
    gem](http://rubyforge.org/projects/text/).
}}

We can calculate the `soundex` key of a string in Ruby with the help of the
[text gem](http://rubyforge.org/projects/text/). To install this gem:

{{code:base
    $> sudo gem install Text
    Successfully installed Text-1.1.2
    1 gem installed
}}

{{code:php
    $result = soundex("hello world");
    var_export($result);
    // => 'H464'
}}

To get the equivalent of the string in PHP, we need to first strip whitespace
from the string.

{{code:ruby
    require 'rubygems'
    require 'text'

    text = "hello world".gsub(/\s/, '')
    p Text::Soundex.soundex(text)
    # => "H464"
}}


{{related:
    strings/levenshtein
    strings/metaphone
}}
