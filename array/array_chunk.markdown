# array_chunk

{{notice:
    This function's solution will only work within the context of the Rails
    framework.
}}

We can split an array into separate chunks in Rails using the
`Array#in_groups_of` method.

{{code:php
    $animals = array('ant', 'bat', 'cat', 'dog', 'elk');
    $result = array_chunk($animals, 3);
    var_export($result);
    // => array(0 => array(0 => 'ant', 1 => 'bat', 2 => 'cat'),
    //          1 => array(0 => 'dog', 1 => 'elk'))
}}

The default Rails implementation of `in_groups_of` will fill any missing
elements with `nil`.

{{code:rails
    animals = ["ant", "bat", "cat", "dog", "elk"]
    p animals.in_groups_of(3)
    # => [["ant", "bat", "cat"], ["dog", "elk", nil]]
}}

To get the same results as our PHP version, we need to pass `false`
as the second argument to `in_groups_of`.

{{code:rails
    animals = ["ant", "bat", "cat", "dog", "elk"]
    p animals.in_groups_of(3, false)
    # => [["ant", "bat", "cat"], ["dog", "elk"]]
}}

