# copy

{{code:php
    $src  = '/path/to/foo';
    $dest = '/path/to/bar';

    copy($src, $dest);
}}

{{code:ruby
    require 'fileutils'

    src  = '/path/to/foo'
    dest = '/path/to/bar'

    FileUtils.cp(src, dest)
}}


{{related:
    filesystem/move_uploaded_file
    filesystem/rename
}}
