# touch

Ruby's `File` class does not have an equivalent of PHP's `touch` function.
However, you can use `FileUtils` from the Ruby Standard Library to a touch
file.

{{code:php
    touch('/path/to/foobar');
}}

{{code:ruby
    require 'fileutils'

    FileUtils.touch '/path/to/foobar'
}}
