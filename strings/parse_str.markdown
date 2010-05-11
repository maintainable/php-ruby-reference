# parse_str
         
{{notice:
    This function's solution requires the Addressable gem.
}}   

PHP's `parse_str` function takes a URL-encoded query string and parses it
into an associative array.  The Ruby equivalent leverages Addressable's
`query_values` method.

{{code:php
    parse_str("foo=bar", $output);
    var_export($output);
    // => array('foo' => 'bar')
    parse_str("foo[]=1&foo[]=2&foo[]=3", $output);
    var_export($output);
    // array('foo' => array(0 => '1', 1 => '2', 2 => '3'))
    parse_str("foo[a]=1&foo[b]=2", $output);
    var_export($output);
    // => array('foo' => array('a' => '1', 'b' => '2'))
}}

{{code:ruby
    require 'addressable/uri'
    Addressable::URI.parse("/?foo=bar").query_values()
    // => {"foo"=>"bar"}
    Addressable::URI.parse("/?foo[]=1&foo[]=2&foo[]=3").query_values()
    // => {"foo"=>["1", "2", "3"]}
    Addressable::URI.parse("/?foo[a]=1&foo[b]=2").query_values()
    // => {"foo"=>{"a"=>"1", "b"=>"2"}}
}}


{{related:
    url/http_build_query
    strings/parse_url
}}
