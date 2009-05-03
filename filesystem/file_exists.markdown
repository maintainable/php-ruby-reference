# file_exists

{{code:php
    $exists = file_exists('/path/to/foobar');
    var_export($exists);

    //=> true
}}

{{code:ruby
    exists = File.exist?('/path/to/foo/')
    p exists

    #=> true
}}

Note that in Ruby 1.8, `File.exist?` is also aliased to `File.exists?`. You
should use `File.exist?` because this alias will be removed in future versions
of Ruby.


{{related:
    filesystem/is_readable
    filesystem/is_writable
    filesystem/is_file
    filesystem/file
}}
