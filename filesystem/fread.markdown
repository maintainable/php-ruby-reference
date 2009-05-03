# fread

To read data from a file in PHP, we call the `fread` function, passing it a
stream resource and an optional number of bytes to read.

{{code:php
    $f = fopen('/path/to/foobar', 'r');
    $bytes = fread($f, 8);
    fclose($f);
}}

To read data from a file in Ruby, we first get a `File` instance and then call
the `File#read` instance method.

{{code:ruby
    bytes = nil
    File.open('/path/to/foobar', 'r') do |f|
      bytes = f.read(8)
    end
}}

In Rails applications, it's a best practice to always open a file by passing a
block as shown above. For more on this, see [fopen](../filesystem/fopen).

Notice that we defined `bytes` above the block. If `bytes` was only defined
inside the block, it would not be available below the block. For an
explanation of how this works, see our article on 
(Ruby Block Scope)[http://railsforphp.com/2008/02/18/ruby-block-scope/].

If your example is simple like this one, you can also use the `File.read` class method.

{{code:ruby
    data = File.read('/path/to/foobar', 8)
}}


{{related:
    filesystem/fwrite
    filesystem/fopen
    filesystem/fsockopen
    filesystem/popen
    filesystem/fgets
    filesystem/fgetss
    filesystem/fscanf
    filesystem/file
    filesystem/fpassthru
}}

