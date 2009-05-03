# symlink

The `symlink` function in PHP creates a symbolic link.

{{code:php
    symlink('/path/to/source', '/path/to/target');
}}

Ruby's `File.symlink` class method is equivalent.

{{code:ruby
    File.symlink('/path/to/source', '/path/to/target')
}}


{{related:                
    filesystem/link         
    filesystem/readlink     
    filesystem/linkinfo
}}
