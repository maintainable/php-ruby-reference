# call_user_func_array

In Ruby we use `Object#send` to invoke a method by name at runtime.
The first argument is the name of the method we're calling, and the rest is a
variable list of arguments to send to that method similar to
`call_user_func` in PHP. We can pass in array of arguments similar
to that in `call_user_func_array` by prefixing the array argument
with a glob operator (`*`). This operator will expand the array to
be passed in as variable arguments.


{{code:php
    function titleize($value, $delim='-')
    {
        return strtolower(str_replace(' ', $delim, $value));
    }

    $args = array('my post title', '-');
    $result = call_user_func_array('titleize', $args);
    var_export($result);
    // => my-blog-post
}}


{{code:ruby
    def titleize(value, delim='-')
      value.gsub(' ', delim).downcase
    end

    args = ["my post title", '-']
    send(:titleize, *args)
    # => my-blog-post
}}


{{related:
    funchand/call_user_func
}}
