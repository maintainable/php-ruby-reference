# stripslashes

You'll rarely need to strip slashes in Ruby, since there is no equivalent of
PHP's magic_quotes_gpc directive. Stripping slashes would be done with
`String#gsub` to do substitution just like
[addslashes](../strings/addslashes).

{{code:php
    $result = stripslashes('I can\\\'t imagine \\"that\\"!\\0');
    var_export($result);
    // => 'I can\'t imagine "that"!\000'
}}

{{code:ruby
    string = "I can\\'t imagine \\\"that\\\"!\\\000"
    p string.gsub("\\", "")
    # => "I can't imagine \"that\"!\000"
}}


{{related:
    strings/addslashes
}}
