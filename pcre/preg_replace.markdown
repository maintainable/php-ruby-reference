# preg_replace

We perform pattern based substitution in Ruby using `String#gsub`, which is
equivalent to PHP's `preg_replace` function. A notable difference is that the
`String#gsub` method is also used for string substitution in Ruby. We do this
by simply providing a string instead of the regular expression pattern. This
would be like using the [str_replace](../strings/str_replace)
function in PHP.

In this example, we want to replace the domain in all emails with `foo`. 


{{code:php
    $string = 'joe@example.com; walter@example.org';
    $result = preg_replace('/@([a-z0-9-]+)/', '@foo', $string);

    var_export($result);
    // => 'joe@foo.com; walter@foo.org'
}}


{{code:ruby
    string = 'joe@example.com; walter@example.org'
    result = string.gsub(/@([a-z0-9-]+)/, '@foo')

    p result
    # => "joe@foo.com; walter@foo.org"
}}


We can use backreferences in our `gsub` replacements just as we would with
`preg_replace` by using `\1`, `\2`, etc in our replacement string.

In this example, we prefix the existing domain with `mail.`. Remember to
escape backslashes used for the backreference.


{{code:php
    // Replace domain with mail.domain
    $string = 'joe@example.com; walter@example.org';
    $result = preg_replace('/@([a-z0-9-]+)/', '@mail.\\1', $string);

    var_export($result);
    // => 'joe@mail.example.com; walter@mail.example.org'
}}


{{code:ruby
    string = 'joe@example.com; walter@example.org'
    result = string.gsub(/@([a-z0-9-]+)/, '@mail.\\1')

    p result
    # => "joe@mail.example.com; walter@mail.example.org"
}}


{{related:
    pcre/preg_match
    pcre/preg_split
}}
