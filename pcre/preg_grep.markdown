# preg_grep

The `preg_grep` function in PHP is a useful function to find
entries in an array that match a given pattern. Ruby does this same operation
with the `grep` method.

In this example, we'll build a new array that only consists of email addresses
that end in `.com`.


{{code:php
    $myArray = array('joe@example.com', 'walter@example.org');
    $result = preg_grep('/\.com$/', $myArray);

    var_export($result);
    // => array('joe@example.com')
}}


{{code:ruby
    my_array = ['joe@example.com', 'walter@example.org']
    result = my_array.grep(/\.com$/)

    p result
    # => ["joe@example.com"]
}}

