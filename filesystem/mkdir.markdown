# mkdir

PHP's `mkdir` function is used to create a new directory. An optional second
argument specifies the permissions on the directory.

{{code:php
    mkdir('/path/to/new_dir', 0700);
}}

Ruby's `Dir.mkdir` class method works exactly the same way. Like PHP's
`mkdir`, it also accepts an optional second argument for permissions.

{{code:ruby
    Dir.mkdir('/path/to/new_dir', 0700)
}}

One nice feature of the `mkdir` function in PHP is that it supports an
optional third argument, `$recursive`, that will recursively build directories
like `mkdir -p` on the shell of Unix-like systems.

{{code:php
    mkdir('/path/to/new_dir', 0700, true);
}}

Ruby's `Dir.mkdir` doesn't have a recursive mode. However, you can use
`FileUtils` from the Ruby Standard Library to make a directory
(`FileUtils.mkdir`) and recursively make a directory (`FileUtils.mkdir_p`).

{{code:ruby
    require 'fileutils'

    # make a directory
    FileUtils.mkdir('/path/to/new_dir')

    # recursively make a directory
    FileUtils.mkdir_p('/path/to/new_dir)
}}

Both `FileUtils.mkdir` and `FileUtils.mkdir_p` allow permissions to be
optionally specified by supplying an options hash.

{{code:ruby
    require 'fileutils'

    FileUtils.mkdir_p('/path/to/new_dir', :mode => 0700)
}}


{{related:
    filesystem/rmdir
}}
