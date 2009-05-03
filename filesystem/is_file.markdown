# is_file

{{code:php
    $is_file = is_file('/path/to/foobar');
    var_export($is_file);

    //=> true
}}

{{code:ruby
    is_file = File.file?('/path/to/foobar')
    p is_file

    #=> true
}}


{{related:
    filesystem/is_dir     
    filesystem/is_link
}}
