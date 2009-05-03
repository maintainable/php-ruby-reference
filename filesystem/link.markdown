# link

The `link` function in PHP creates a hard link.

{{code:php
    link('/path/to/source', '/path/to/target');
}}

Ruby's `File.link` class method is equivalent.

{{code:ruby
    File.link('/path/to/source', '/path/to/target')
}}


{{related:                
    filesystem/symlink      
    filesystem/readlink     
    filesystem/linkinfo
}}
