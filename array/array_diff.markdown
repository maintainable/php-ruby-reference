# array_diff

We can find the difference between two arrays using the `-` (subtract) method.
This method returns a new array that is a copy of the original array `animals1`,
removing any items that also appear in other array `animals2`.

{{code:php
    $animals1 = array('cat', 'dog', 'bat', 'rat');
    $animals2 = array('cat', 'dog');

    $result = array_diff($animals1, $animals2);
    var_export($result);
    // => array(2 => 'bat', 3 => 'rat')
}}

{{code:ruby
    animals1 = ['cat', 'dog', 'bat', 'rat']
    animals2 = ['cat', 'dog']

    p animals1 - animals2
    # => ["bat", "rat"]
}}


{{related:
    array/array_diff_assoc    
    array/array_intersect     
    array/array_intersect_assoc
}}
