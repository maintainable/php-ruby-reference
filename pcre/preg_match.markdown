# preg_match

We match a pattern in Ruby strings using the `match` method. Ruby's `match`
method works differently than `preg_match` in how it returns matches. We
usually want to know two different things when we match data: If the pattern
matched, and what specific strings sections were matched.

PHP returns an integer to tell us if the data matched (either `0` or `1`) and
populates a matches array by reference. Ruby returns a `MatchData` object when
the pattern matches, and `nil` when something doesn't. We can inspect the
`MatchData` object to find the actual string matches.

In this example, we try to match the different components of a list of email
addresses. Both `preg_match` and `String#match` only match the first
occurrence of the pattern.


{{code:php
    $string = 'joe@example.com; walter@example.org';
    $result = preg_match('/([a-z0-9_.-]+)@([a-z0-9-]+)\.([a-z.]+)/i', 
              $string, $matches);
    var_export($result); 
    // => 1

    var_export($matches); 
    // => array('joe@example.com', 'joe', 'example', 'com')
}}


{{code:ruby
    string = 'joe@example.com; walter@example.org'
    matches = string.match(/([a-z0-9_.-]+)@([a-z0-9-]+)\.([a-z.]+)/i)
    p !matches.nil?
    # => true

    p matches
    # => #<MatchData:0x1ed138>

    p matches[1]
    # => "joe"

    p matches.to_a
    # ["joe@example.com", "joe", "example", "com"]
}}


{{related:
    pcre/preg_match_all
    pcre/preg_replace 
    pcre/preg_split
}}
