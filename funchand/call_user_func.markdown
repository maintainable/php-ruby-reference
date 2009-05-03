# call_user_func

In Ruby we use `Object#send` to invoke a method by name at runtime. The first
argument is the name of the method we're calling, and the rest is a variable
list of arguments to send to that method similar to `call_user_func` in PHP.


{{code:php
    function titleize($value, $delim='-')
    {
        return strtolower(str_replace(' ', $delim, $value));
    }

    $result = call_user_func('titleize', 'my post title', '-');
    var_export($result);
    // => my-blog-post
}}


{{code:ruby
    def titleize(value, delim='-')
      value.gsub(' ', delim).downcase
    end

    send(:titleize, "my post title", '-')
    # => my-blog-post
}}


{{related:
    funchand/call_user_func_array
    var/is_callable
}}
