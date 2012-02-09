# is_dir

{{code:php
    $is_dir = is_dir('/path/to/foobar');
    var_export($is_dir);

    //=> true
}}

{{code:ruby
    is_dir = File.directory?('/path/to/foobar')
    p is_dir

    #=> true
}}


{{related:
    dir/chdir                 
    filesystem/dir            
    filesystem/opendir        
    filesystem/is_file   
    filesystem/is_link
}}
