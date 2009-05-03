# lchgrp

{{notice:
    This function's solution assumes a Unix-like operating system.
}}


The `lchgrp` function in PHP will change the group of a file to a different
group ID, assuming the PHP process has sufficient privileges to do so. It is
the same as PHP's `chgrp`, but it does not follow the last symbolic link.
Instead, it changes the link itself.

{{code:php
    lchgrp('/path/to/foobar', 501);
}}

Ruby's `File.lchown` class method is used to accomplish the same task.

{{code:ruby
    File.lchown(nil, 501, '/path/to/foobar')
}}

The first argument of `File.lchown` is the user, the second is the group, and
the third is the file. Above, the user is set to `nil`. This will leave the
user unchanged.

## Changing the Group by Name

One nice feature of PHP's `lchgrp` is that the `$group` argument is mixed. It
can accept either a group ID or a group name.

{{code:php
    lchown('/path/to/foobar', 'herbert');
}}

`File.lchown` from Ruby is not as flexible. It only accepts numeric IDs. To
change the group by name, we must first perform a lookup to get the group ID
from the name.

The `Etc` module from the Ruby Standard Library contains a method `getgrnam`
that returns a `Struct` of information about a group by name, which includes
the group ID. We can use this lookup the group ID and then pass it to
`File.lchown`.

{{code:ruby
    require 'etc'

    gid = Etc.getgrnam('herbert').gid
    File.lchown(nil, gid, '/path/to/foobar')
}}


{{related:
    filesystem/chgrp          
    filesystem/lchown         
    filesystem/chown          
    filesystem/chmod
}}
