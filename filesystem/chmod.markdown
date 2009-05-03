# chmod

{{code:php
    chmod('/path/to/file', 0644);
}}

{{code:ruby
    File.chmod(0644, '/path/to/file')
}}

Notice the leading zero in both examples (`0644`). Both PHP and Ruby have
built-in support for octal numbers, the traditional way of representing file
permissions on Unix-like systems. Be sure to include the leading zero so your
results are as you intended.

{{code:ruby
    File.chmod(0644, '/path/to/file', '/path/to/another')
}}                          

Ruby's `File.chmod` method accepts the mode as the first argument and supports
one or more paths as variable arguments. This is convenient for changing
multiple files in one call.


{{related:
    filesystem/chown
    filesystem/chgrp
}}
