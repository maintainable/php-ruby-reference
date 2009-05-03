# fseek

{{code:php
    $f = fopen('/path/to/foobar.txt', 'r');
    fseek($f, 3);
    // do something at position 3
    fclose($f);
}}

{{code:ruby
    File.open('/path/to/foobar.txt', 'r') do |f|
      f.seek(3)
      # do something at position 3
    end
}}

Both PHP's `fseek` and Ruby's `File#seek` support an optional third argument
that specifies the seek behavior. This argument takes constants that are
virtually identical in both name and behavior between PHP and Ruby.

<div class="compare">
    <table cellspacing="0">
        <tr>
            <th>PHP</th><th>Ruby</th>
        </tr>
        <tr>
            <td>SEEK_SET</td><td>IO::SEEK_SET</td>
        </tr>
        <tr>
            <td>SEEK_CUR</td><td>IO::SEET_CUR</td>
        </tr>
        <tr>
            <td>SEEK_END</td><td>IO::SEEK_END</td>
        </tr>
    </table>
</div>

If you are doing an absolute seek (`IO::SEEK_SET`) you might find it more
convenient to use `File#pos=`.

{{code:ruby
    # all three are equivalent
    f.seek(3)
    f.seek(3, IO::SEEK_SET)
    f.pos = 3
}}


{{related:                
    filesystem/ftell
    filesystem/rewind
}}
