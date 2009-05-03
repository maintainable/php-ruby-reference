# getcwd

PHP's `getcwd` function returns the path to the current working directory as a
string.


{{code:php
    $cwd = getcwd();
    var_export($cwd);
    //=> "/path/to/foo"
}}


Ruby's `Dir.pwd` method is equivalent.


{{code:ruby
    cwd = Dir.pwd
    p cwd
    #=> "/path/to/foo"
}}


{{related:
    dir/chdir
    filesystem/chmod
    outcontrol/flush
}}

