# unlink

The `unlink` function in PHP is used to delete a file from the filesystem.
Ruby's `File.unlink` class method is equivalent.

{{code:php
    unlink('/path/to/foobar')
}}

{{code:ruby
    File.unlink('/path/to/foobar')
}}

`File.unlink` is also aliased as `File.delete`. Both are commonly used.

In both the PHP and Ruby versions, the filename must refer to only a single
file. For example, `foo*` would not be a valid argument.

## Deleting Multiple Files

Ruby's `File.unlink` supports variable arguments. You may specify multiple
filenames to delete in a single call.

{{code:ruby
    File.unlink('/path/to/foo', '/path/to/bar', '/path/to/baz')
}}

## Deleting by Pattern Match

An alternative to `File.unlink` is `FileUtils.rm`. You may pass either a
string filename to `FileUtils.rm` or an array of filenames. This makes it
especially useful for deleting multiple files when combined with `Dir.glob`.

{{code:ruby
    require 'fileutils'

    FileUtils.rm Dir.glob('/path/to/*')
}}


{{related:
    filesystem/rmdir
}}
