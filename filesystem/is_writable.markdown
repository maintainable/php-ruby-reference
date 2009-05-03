# is_writable

{{code:php
    $writable = is_writable('/path/to/foobar');
    var_export($writable);

    //=> true
}}

{{code:ruby
    writable = File.writable?('/path/to/foobar')
    p writable

    #=> true
}}


{{related:
    filesystem/is_readable    
    filesystem/file_exists    
    filesystem/fwrite
}}
