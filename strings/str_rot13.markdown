# str_rot13

There is no native rot13 method in Ruby, but we can easily get the same
results using `String#tr`.

{{code:php
    $result = str_rot13('Hello world');
    var_export($result);
    // => 'Uryyb jbeyq'
}}

{{code:ruby
    p "Hello world".tr("A-Za-z", "N-ZA-Mn-za-m")
    # => "Uryyb jbeyq"
}}


{{related:
    strings/strtr
}}
