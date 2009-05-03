# array_diff

We can find the difference between two arrays using the `Enumerable#reject`
method. This method rebuilds an array based on conditions that are evaluated
in a block. In the block we simply reject any element of the array that is in
the comparison array.

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

    p animals1.reject {|a| animals2.include?(a) }
    # => ["bat", "rat"]
}}


{{related:
    array/array_diff_assoc    
    array/array_intersect     
    array/array_intersect_assoc
}}
