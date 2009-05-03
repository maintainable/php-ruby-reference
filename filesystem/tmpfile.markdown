# tmpfile

PHP's `tmpfile` function returns a resource to a temporarily file, opened with
mode `w+`.

{{code:php
    $f = tmpfile();
    fwrite($f, 'foo');
    rewind($f);

    var_export(fread($f));
    //=> 'foo'

    fclose($f);
}}

Ruby's `Tempfile` class is a special kind of `File` that accomplishes the same
task.

Unlike PHP's `tmpfile` which names the file without any parameters, you must
specify a prefix that `Tempfile` will use to build the filename.

{{code:ruby
    require 'tempfile'

    Tempfile.open('prefix') do |f|
      f.write('foo')
      f.rewind

      p f.read
      #=> "foo"

      f.unlink
    end
}}

Like any other `File` in Ruby, it's a best practice in Rails applications to
always open `Tempfile` instances with a block as shown above. For more on
this, please see [fopen](../filesystem/fopen).

In PHP, the file is automatically unlinked when closed or at the end of the
request. In Ruby, this is not the case, even within the context of the Rails
framework.

Instead, `Tempfile` defines a finalizer which unlinks the file. However, the
finalizer will not be called until the object is deferenced and collected by
Ruby's garbage collector. Since the garbage collection interval is
indeterminate, we recommend that you always explicitly `unlink` any `Tempfile`
when you are done with it.


{{related:
    filesystem/tempnam
    filesystem/sys_get_temp_dir
}}
