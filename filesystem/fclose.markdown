# fclose

To close a file in PHP, you pass its stream resource to `fclose`.

{{code:php
    $f = fopen('/path/to/foobar', 'w');
    fwrite($f, 'chars');
    fclose($f);
}}

Similarly, if you use Ruby's `File.open` method to return a file instance, you
need to call the `close` method on that instance.

{{code:ruby
    f = File.open('/path/to/foobar', 'w')
    f.write 'chars'
    f.close
}}

Alternatively, you can have Ruby automatically close files that you open by
passing a block to the `File.open` method:

{{code:ruby
    File.open('/path/to/foobar', 'w') do |f|
      f.write 'chars'
    end
}}

Using a block in this way is considered a best practice in Rails applications.
For more on this, please see [fopen](../filesystem/fopen).


{{related:                
    filesystem/fopen        
    filesystem/fsockopen
}}
