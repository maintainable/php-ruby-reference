# chown

{{notice:
    This function's solution assumes a Unix-like operating system.
}}

The `chown` function in PHP will change the owner of a file to a different
user ID, assuming the PHP process has sufficient privileges to do so.

{{code:php
    chown('/path/to/foobar', 501);
}}

Ruby's `File.chown` class method is used to accomplish the same task.

{{code:ruby
    File.chown(501, nil, '/path/to/foobar')
}}

The first argument of `File.chown` is the user, the second is the group, and
the third is the file. Above, the group is set to `nil`. This will leave the
group unchanged.

## Changing the Owner by User Name

One nice feature of PHP's `chown` is that the `$user` argument is mixed. It
can accept either a user ID or a user name.

{{code:php
    chown('/path/to/foobar', 'herbert');
}}

`File.chown` from Ruby is not as flexible. It only accepts numeric IDs. To
change the user by name, we must first perform a lookup to get the user ID
from the name.

The `Etc` module from the Ruby Standard Library contains a method `getpwnam`
that returns a `Struct` of information about a user by name, which includes
the user ID. We can use this lookup the user ID and then pass it to
`File.chown`.

{{code:ruby
    require 'etc'

    uid = Etc.getpwnam('herbert').uid
    File.chown(uid, nil, '/path/to/foobar')
}}

## Changing the Owner with FileUtils

An alternative to using `File` and `Etc` to change the owner of a file is to
use `FileUtils`, also from the Ruby Standard Library. `FileUtils.chown` can
change the owner by either user ID or name.

{{code:ruby
    require 'fileutils'

    # equivalent
    FileUtils.chown(501, nil, '/path/to/foobar')
    FileUtils.chown('herbert', nil, '/path/to/foobar')
}}

The first argument of `FileUtils.chown` is the user, the second is the group,
and the third is the file. Above, the group is set to `nil`. This will leave
the group unchanged.

Another useful method is `FileUtils.chown_R`, whose usage is the same but will
recursively change all files in a given path.


{{related:
    filesystem/chmod
}}
