# preg_replace_callback

We can implement a callback for regular expression replacement by passing a
block to `String#gsub`. Matches are passed as block arguments.

                      
{{code:php
    function func($matches)
    {
        return strtoupper($matches[0]);
    }
    $string = 'joe@example.com; walter@example.org';
    $result = preg_replace_callback('/@([a-z0-9-]+)/', 'func', $string);

    var_export($result);
    // => 'joe@EXAMPLE.com; walter@EXAMPLE.org'
}}


{{code:ruby
    def my_method(match)
      match.upcase
    end

    my_string = "joe@example.com; walter@example.org"
    p my_string.gsub(/@([a-z0-9-]+)/){ |match| my_method(match) }
    # => "joe@EXAMPLE.com; walter@EXAMPLE.org"
}}


{{related:
    pcre/preg_replace
    funchand/create_function
}}
