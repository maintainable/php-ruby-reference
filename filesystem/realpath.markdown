# realpath

{{code:php
    $absPath = realpath('../to/foobar');
    var_export($absPath);

    //=> '/absolute/path/to/foobar'
}}

{{code:ruby
    require 'pathname'
    abs_path = Pathname.new('../to/foobar').realpath.to_s
    p abs_path

    #=> "/absolute/path/to/foobar"
}}


{{related:
    filesystem/basename       
    filesystem/dirname        
    filesystem/pathinfo
}}
