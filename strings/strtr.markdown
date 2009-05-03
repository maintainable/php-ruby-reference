# strtr

Translating certain characters in a string in Ruby works pretty similar in
Ruby to that in PHP. Ruby uses the `String#tr` method to perform translations.
The Ruby method does not accept an array as an argument like it does in PHP.

{{code:php
    $result = strtr("cat", "abc", "zyx");
    var_export($result);
    // => 'xzt'
}}

{{code:ruby
    p "cat".tr("abc", "zyx")
    # => "xzt"
}}


{{related:
    pcre/preg_replace
    strings/str_replace
}}
