# nl2br

Adding a `<br />` tag before each newline is accomplished in Ruby using string
substitution with `String#gsub`.

{{code:php
    $result = nl2br("The quick\nbrown fox");
    var_export($result);
    // => "The quick<br />\nbrown fox"
}}

{{code:ruby
    p "The quick\nbrown fox".gsub("\n", "<br />\n")
    # => "The quick<br />\nbrown fox"
}}


{{related:
    strings/htmlentities
    strings/htmlspecialchars
    strings/wordwrap
    strings/str_replace
}}
