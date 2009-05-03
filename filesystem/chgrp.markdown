# chgrp

{{notice:
    This function's solution assumes a Unix-like operating system.
}} 

The `chgrp` function in PHP will change the group of a file to a different
group ID, assuming the PHP process has sufficient privileges to do so.

{{code:php
    chgrp('/path/to/foobar', 501);
}}

Ruby's `File.chown` class method is used to accomplish the same task.

{{code:ruby
    File.chown(nil, 501, '/path/to/foobar')
}}

The first argument of `File.chown` is the user, the second is the group, and
the third is the file. Above, the user is set to `nil`. This will leave the
user unchanged.

## Changing the Group by Name

One nice feature of PHP's `chown` is that the `$group` argument is mixed. It
can accept either a group ID or a group name.

{{code:php
    chown('/path/to/foobar', 'herbert');
}}

`File.chown` from Ruby is not as flexible. It only accepts numeric IDs. To
change the group by name, we must first perform a lookup to get the group ID
from the name.

The `Etc` module from the Ruby Standard Library contains a method `getgrnam`
that returns a `Struct` of information about a group by name, which includes
the group ID. We can use this lookup the group ID and then pass it to
`File.chown`.

{{code:ruby
    require 'etc'

    gid = Etc.getgrnam('herbert').gid
    File.chown(nil, gid, '/path/to/foobar')
}}

## Changing the Group with FileUtils

An alternative to using `File` and `Etc` to change the group of a file is to
use `FileUtils`, also from the Ruby Standard Library. `FileUtils.chown` can
change the group by either group ID or name.

{{code:ruby
    require 'fileutils'

    # equivalent
    FileUtils.chown(nil, 501, '/path/to/foobar')
    FileUtils.chown(nil, 'herbert', '/path/to/foobar')
}}

The first argument of `FileUtils.chown` is the user, the second is the group,
and the third is the file. Above, the user is set to `nil`. This will leave
the user unchanged.

Another useful method is `FileUtils.chown_R`, whose usage is the same but will
recursively change all files in a given path.


{{related:
    filesystem/chown
    filesystem/chmod
}}
