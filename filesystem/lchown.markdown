# lchown

{{notice:
    This function's solution assumes a Unix-like operating system.
}}

The `lchown` function in PHP will change the owner of a file to a different
user ID, assuming the PHP process has sufficient privileges to do so. It is
the same as PHP's `chown`, but it does not follow the last symbolic link.
Instead, it changes the link itself.

{{code:php
    lchown('/path/to/foobar', 501);
}}

Ruby's `File.lchown` class method is used to accomplish the same task.

{{code:ruby
    File.lchown(501, nil, '/path/to/foobar')
}}

The first argument of `File.lchown` is the user, the second is the group, and
the third is the file. Above, the group is set to `nil`. This will leave the
group unchanged.

## Changing the Owner by User Name

One nice feature of PHP's `lchown` is that the `$user` argument is mixed. It
can accept either a user ID or a user name.

{{code:php
    lchown('/path/to/foobar', 'herbert');
}}

`File.lchown` from Ruby is not as flexible. It only accepts numeric IDs. To
change the user by name, we must first perform a lookup to get the user ID
from the name.

The `Etc` module from the Ruby Standard Library contains a method `getpwnam`
that returns a `Struct` of information about a user by name, which includes
the user ID. We can use this lookup the user ID and then pass it to
`File.chown`.

{{code:ruby
    require 'etc'

    uid = Etc.getpwnam('herbert').uid
    File.lchown(uid, nil, '/path/to/foobar')
}}


{{related:                
    filesystem/chgrp      
    filesystem/lchgrp     
    filesystem/chown      
    filesystem/chmod
}}
