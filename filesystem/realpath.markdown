# realpath

{{code:php
    $absPath = realpath('../to/foobar');
    var_export($absPath);

    //=> '/absolute/path/to/foobar'
}}

{{code:ruby
    abs_path = File.expand_path('../to/foobar')
    p abs_path

    #=> "/absolute/path/to/foobar"
}}


{{related:
    filesystem/basename       
    filesystem/dirname        
    filesystem/pathinfo
}}
