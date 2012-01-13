# sys_get_temp_dir

Returns directory path used for temporary files.

{{code:php
  $tmp = sys_get_temp_dir();
  var_export($tmp);

  //=> '/tmp'
}}

{{code:ruby
  require 'tmpdir'
  tmp = Dir.tmpdir
  p tmp

  #=> "/tmp"
}}

{{related:
    filesystem/basename
    filesystem/dirname
    filesystem/pathinfo
}}
