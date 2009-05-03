# is_link
         
{{code:php
    $symlinked = is_link('/path/to/foobar');
    var_export($symlinked);

    //=> true
}}

{{code:ruby
    symlinked = File.symlink?('/path/to/foobar')
    p symlinked

    #=> true
}}


{{related:                
    filesystem/is_dir       
    filesystem/is_file      
    filesystem/readlink
}}
