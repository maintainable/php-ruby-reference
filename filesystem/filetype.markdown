# filetype

PHP's `filetype` performs a `stat` on a file and returns a string representing
its type.

{{code:php
    $type = filetype('/path/to/foobar');
    var_export($type);
    //=> "file"
}}

The `File.ftype` class method in Ruby performs the same task.   

{{code:ruby
    type = File.ftype('/path/to/foobar')
    p type
    #=> "file"
}}

This table shows the strings returned by each version.

<div class="compare">
    <table cellspacing="0">
        <tr>
            <th>PHP</th><th>Ruby</th>
        </tr>
        <tr>
            <td>link</td><td>link</td>
        </tr>
        <tr>
            <td>fifo</td><td>fifo</td>
        </tr>
        <tr>
            <td>char</td><td>characterSpecial</td>
        </tr>
        <tr>
            <td>dir</td><td>directory</td>
        </tr>
        <tr>
            <td>block</td><td>blockSpecial</td>
        </tr>
        <tr>
            <td>file</td><td>file</td>
        </tr>
        <tr>
            <td>socket</td><td><i>No equivalent</i></td>
        </tr>
        <tr>
            <td>unknown</td><td>unknown</td>
        </tr>
    </table>
</div> 

## Checking for a Specific File Type

Perhaps the most common usage of `filetype` is to check if a path is a
specific type, such as this example which checks if the path is a `dir`.

{{code:php
    if (filetype('/path/to/foobar') == 'dir') {
      // ...
    }
}}

You can do this with the string returned by `File.ftype` as well but `File`
also provides convenience methods like `file?` and `directory?` that make code
more readable.

{{code:ruby
    if File.directory?('/path/to/foobar')
      # ...
    end
}}

## Working with File::Stat Instances

The `File::Stat` instance returned by Ruby's `File.stat` also supports the
methods shown above and more.

{{code:ruby
    stat = File.stat('/path/to/foobar')
    p stat.ftype

    #=> "file"
}}

{{code:ruby
    stat = File.stat('/path/to/foobar')
    if stat.directory?('/path/to/foobar')
      # ...
    end
}}


{{related:
    filesystem/is_dir         
    filesystem/is_file
    filesystem/is_link
    filesystem/file_exists
    filesystem/stat
    filesystem/mime_content_type
}}                        
