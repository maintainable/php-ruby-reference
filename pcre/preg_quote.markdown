# preg_quote

When we use a string as a regular expression, we want to escape the characters
that could be interpreted as regexp special characters. PHP does this using
`preg_quote`, and Ruby has an equivalent `Regexp.escape` method.

In this example, we'll escape any regular expression special character in the
given string.


{{code:php
    $string = '[my_file.gif]';
    $result = preg_quote($string);

    var_export($result);
    // => '\\[my_file\\.gif\\]'
}}


{{code:php
    string = '[my_file.gif]'
    result = Regexp.escape(string)

    p result
    # => "\\[my_file\\.gif\\]"
}}
