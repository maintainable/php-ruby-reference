# is_executable

{{code:php
    $executable = is_executable('/path/to/foobar');
    var_export($executable);

    //=> true
}}

{{code:ruby
    executable = File.executable?('/path/to/foobar')
    p executable

    #=> true
}}


{{related:                
    filesystem/is_file      
    filesystem/is_link
}}
