# printf

Outputting a formatted string works nearly identical in Ruby using `printf`.

{{code:php
    printf("The %s is %d feet tall", "man", 6);
    // => The man is 6 feet tall
}}

{{code:ruby
    printf("The %s is %d feet tall", "man", 6)
    # => The man is 6 feet tall
}}


{{related:
    strings/print
    strings/sprintf
    strings/vprintf
    strings/sscanf
    strings/fscanf
    strings/flush
}}
