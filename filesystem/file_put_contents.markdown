# file_put_contents

PHP has a convenience function called `file_put_contents` that automatically
opens a file for writing, writes the contents of a string into it, and then
closes the file.

We can accomplish the same task in Ruby by opening a file for writing and
passing a block that writes the contents. The file will be automatically
closed when the block exits.

{{code:php
    $contents = 'hello';
    file_put_contents('/path/to/foobar', $contents);
}}

{{code:ruby
    contents = 'hello'
    File.open('/path/to/foobar', 'w') do |f|
      f.write contents
    end
}}


{{related:
    filesystem/fopen
    filesystem/fwrite
    filesystem/file_get_contents
    filesystem/stream_context_create
}}
