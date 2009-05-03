# strtok

We can tokenize a string in Ruby using the `String#split` method along with a
regular expression.

{{code:php
    $tok = strtok("This is\tan\nexample", " \n\t");
    while ($tok !== false) {
        $tokens[] = $tok;
        $tok = strtok(" \n\t");
    }
    var_export($tokens);
    // => array(0 => 'This', 1 => 'is', 2 => 'an', 3 => 'example')
}}

{{code:ruby
    p "This is\tan\nexample".split(/[\n\t ]/)
    # => ["This", "is", "an", "example"]
}}


{{related:
    strings/explode
    regex/split
}}
