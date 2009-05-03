# htmlspecialchars_decode

Unescaping a string that has been escaped for HTML can be done using the
`CGI.unescapeHTML` class method.

{{code:php
    $result = htmlspecialchars_decode("test &quot;unescaping&quot; &lt;characters&gt;"); 
    var_export($result);
    // => 'test "escaping" <characters>'
}}

{{code:ruby
    require 'cgi'

    p CGI.unescapeHTML("test &quot;unescaping&quot; &lt;characters&gt;")
    # => "test \"unescaping\" <characters>"
}}


{{related:
    strings/htmlspecialchars
    strings/html_entity_decode
}}
