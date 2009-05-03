In Ruby, we use the `CGI` class to encode a URL. We first need to require the
`CGI` library using `require "cgi"`. This is similar to using `require_once`
to include a class in PHP.

To get the equivalent result of PHP's `urlencode` function, we'll use the
`CGI.escape` class method.


{{code:php
    $result = urlencode("Hello <b>there!</b>");
    var_export($result);
    // => 'Hello+%3Cb%3Ethere%21%3C%2Fb%3E'
}}


{{code:ruby
    require 'cgi'

    p CGI.escape("Hello <b>there!</b>")
    # => "Hello+%3Cb%3Ethere%21%3C%2Fb%3E"
}}


{{related:
    url/urldecode 
    strings/htmlentities 
    url/rawurlencode 
    url/rawurldecode
}}
