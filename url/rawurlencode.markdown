In Ruby, we use the `CGI` class to encode a URL. We first need to require the
`CGI` library using `require "cgi"`. This is similar to using `require_once`
to include a class in PHP.

To get the closest equivalent of the result of PHP's `rawurlencode` function,
we'll use the `CGI.escape` class method.

The `rawurlencode` function in PHP encodes according to the 
[RFC 1738](http://www.faqs.org/rfcs/rfc1738) spec, and uses `%20` to
encode spaces instead of a plus (`+`) character. If you want to encode your
URLs according to RFC 1738, you'll need to use `String#gsub` to replace the
`+` character with `%20`.

                                            
{{code:php
    $result = rawurlencode("Hello <b>there!</b>");
    var_export($result);
    // => 'Hello%20%3Cb%3Ethere%21%3C%2Fb%3E'
}}


{{code:ruby
    require 'cgi'

    p CGI.escape("Hello <b>there!</b>").gsub("+", "%20")
    # => "Hello%20%3Cb%3Ethere%21%3C%2Fb%3E"
}}


{{related:
    url/rawurldecode
    url/urldecode
    url/urlencode
}}
