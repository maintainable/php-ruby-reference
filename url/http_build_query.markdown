# http_build_query
         
{{notice:
    This function's solution will only work within the context of the Rails
    framework.
}}   

PHP's `http_build_query` function provides a convenient way to
generate URL-encoded query strings from associative arrays.
                        

{{code:php
    $data = array('foo' => array('bar' => 'baz'));
    $query = http_build_query($data);
    var_export($query);

    //=> 'foo%5Bbar%5D=baz'
}}


In Rails, we can use ActiveSupport's `Hash#to_query` method.


{{code:rails
    data = {:foo => {:bar => 'baz'}}
    p data.to_query

    #=> "foo%5Bbar%5D=baz"
}}


{{related:
    url/urldecode
}}
