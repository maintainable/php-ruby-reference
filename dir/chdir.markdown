# chdir

The `chdir` function in PHP changes the current working directory.


{{code:php
    chdir('/path/to/foo');
}}


Ruby's `Dir.chdir` is equivalent.


{{code:ruby
    Dir.chdir('/path/to/foo')
}}


## Temporarily Changing the Directory

Often times, you'll want to change to a directory to perform some operations
and then return to the directory you started from. In PHP, you can do this by
storing the current working directory in a variable before calling
`chdir`.


{{code:php
    $start = getcwd();
    chdir('/path/to/foo');
    // perform some operations
    chdir($start);
}}


Ruby's blocks provide a convenient shortcut. If you pass a block to
`Dir.chdir`, the directory will be changed before yielding to the
block and then original working directory restored when the block exits.


{{code:ruby
    Dir.chdir('/path/to/foo') do
      # perform some operations
    end
}}


{{related:
    dir/getcwd 
    outcontrol/flush
}}
