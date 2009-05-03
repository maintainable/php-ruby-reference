# sprintf

Returning a formatting string is done nearly identical in Ruby as PHP using
the `sprintf` method.

{{code:php
    $s = sprintf("The %s is %d feet tall", "man", 6);
    print $s;
    // => The man is 6 feet tall
}}

{{code:ruby
    s = sprintf("The %s is %d feet tall", "man", 6)
    puts s
    # => The man is 6 feet tall
}}


{{related:
    strings/printf
    strings/number_format
    strings/sscanf
    strings/fscanf
    strings/vsprintf
}}
