# rmdir

We can remove a directory in PHP using the `rmdir` function. The
directory must be empty and permissions must allow its removal.

{{code:php
    rmdir('/path/to/dir_to_remove');
}}

Ruby's `Dir` class provides two class methods, `Dir.delete` and `Dir.rmdir`,
that are synonyms. Both are functionally equivalent to PHP's `rmdir`.

{{code:ruby
    # identical
    Dir.delete('/path/to/dir_to_remove')
    Dir.rmdir('/path/to/dir_to_remove')
}}

One drawback of both PHP's `rmdir` and the class methods provided by Ruby's
`Dir` class is that directory must be empty before it can be removed.

You can remove a non-empty directory, in the same way as you would with `rm
-rf` on the shell of a Unix-like system, by using `FileUtils.rm_rf`.

{{code:ruby
    require 'fileutils'

    FileUtils.rm_rf('/path/to/dir_to_remove')
}}


{{related:
    filesystem/mkdir
    filesystem/unlink
}}

