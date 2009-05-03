# preg_split

We split strings by a pattern in Ruby using the `String#split` method. As with
`String#gsub`, we can also use this same method to split using a string
instead of a regular expression. This means that `split` also performs the
equivalent of the `explode` function in PHP.

In this example, we create an array of the list of emails by splitting the
string using the semi-colon and space as the delimiter.


{{code:php
    $string = 'joe@example.com; walter@example.org';
    $result = preg_split('/;\s?/', $string);
  
    var_export($result);
    // array('joe@example.com', 'walter@example.org')
}}


{{code:ruby
    string = 'joe@example.com; walter@example.org'
    result = string.split(/;\s?/)

    p result
    # => ["joe@example.com", "walter@example.org"]
}}


{{related:
    strings/implode
    pcre/preg_match
    pcre/preg_match_all
    pcre/preg_match 
    pcre/preg_replace
}}
