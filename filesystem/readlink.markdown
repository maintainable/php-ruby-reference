# readlink

The `readlink` function in PHP returns the target of a symbolic link.

{{code:php
    $target = readlink('/path/to/bar');
    var_export($target);

    //=> "/path/to/foo"
}}

Ruby's `File.readlink` is equivalent.

{{code:ruby
    target = File.readlink('/path/to/bar')
    p target

    #=> "/path/to/foo"
}}


{{related:
    filesystem/is_link
    filesystem/symlink
    filesystem/linkinfo
}}
