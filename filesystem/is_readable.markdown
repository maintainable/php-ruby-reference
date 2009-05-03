# is_readable

{{code:php
    $readable = is_readable('/path/to/foobar');
    var_export($readable);

    //=> true
}}

{{code:ruby
    readable = File.readable?('/path/to/foobar')
    p readable

    #=> true
}}


{{related:
    filesystem/is_writable    
    filesystem/file_exists    
    filesystem/fgets
}}
