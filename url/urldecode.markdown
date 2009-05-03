In Ruby, we use the `CGI` class to decode a URL. We first need to require the
`CGI` library using `require "cgi"`. This is similar to using `require_once`
to include a class in PHP.

To get the equivalent result of PHP's `urldecode` function, we'll use the
`CGI.unescape` class method.


{{code:php
    $result = urldecode('Hello+%3Cb%3Ethere%21%3C%2Fb%3E');
    var_export($result);
    // => 'Hello <b>there!</b>'
}}


{{code:ruby
    require 'cgi'

    p CGI.unescape("Hello+%3Cb%3Ethere%21%3C%2Fb%3E")
    # => "Hello <b>there!</b>"
}}


{{related:
    url/urlencode 
    url/rawurlencode 
    url/rawurldecode
}}


