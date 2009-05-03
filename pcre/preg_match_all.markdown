# preg_match_all

PHP returns an integer with the number of matches for `preg_match_all` and
populates a matches array by reference. Ruby performs multiple matches for a
string using the `String#scan` method. This method returns a nested array of
matches or an empty array when no matches are found. Be aware that the nesting
of values in this array is different than how `preg_match_all` orders matches.

In this example, we match components of the email address, and both
`preg_match_all` and `String#scan` give us an array of matches that are found.


{{code:php
    $string = 'joe@example.com; walter@example.org';
    $result = preg_match_all('/([a-z0-9_.-]+)@([a-z0-9-]+)\.[a-z.]+/i', 
              $string, $matches);
    var_export($result);
    // => 2

    var_export($matches);
    // => array(array('joe@example.com', 'walter@example.org'),
    //          array('joe',             'walter'),
    //          array('example',         'example'),
}}


{{code:ruby
string = 'joe@example.com; walter@example.org'
result = string.scan(/([a-z0-9_.-]+)@([a-z0-9-]+)\.[a-z.]+/i)
p result.size
# => 2

p result
# => [["joe", "example"], ["walter", "example"]]
}}


{{related:
    pcre/preg_match           
    pcre/preg_replace         
    pcre/preg_split
}}
