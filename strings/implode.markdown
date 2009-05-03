# implode

Joining array elements using a string is done in Ruby using the `Array#join`
method.

{{code:php
    $result = implode('; ', array('derek@example.com', 'mike@example.com'));
    var_export($result);
    // => 'derek@example.com; mike@example.com'
}}

{{code:ruby
    p ['derek@example.com', 'mike@example.com'].join("; ")
    # => "derek@example.com; mike@example.com"
}}


{{related:
    strings/explode
}}
