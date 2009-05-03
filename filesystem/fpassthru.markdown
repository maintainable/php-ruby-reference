# fpassthru

The `fpassthru` function in PHP reads all data remaining on a stream resource
and sends it to the output buffer.

{{code:php
    $f = fopen('/path/to/foobar');
    passthru($f);
    fclose($f);
}}

Ruby does not have an equivalent method. If the file is relatively small, you
can read the entire file with `File.read` and then print it.

{{code:ruby
    STDOUT.write File.read('/path/to/foobar')
}}

For larger files, you might want to read the file in chunks to avoid loading
the entire file into memory.

{{code:ruby
    File.open('/path/to/foobar', 'r') do |f|
      STDOUT.write(f.read(8192)) until f.eof
    end
}}

## ActionController

The examples above assume a standalone Ruby environment. Within the context of
the Rails framework, you can render a file from a controller action using the
`render` method.

{{code:rails
  class DemoController < ApplicationController
    def index
      render :file => '/path/to/foobar'
    end
  end
}}


{{related:
    filesystem/readfile
    filesystem/fopen
    filesystem/popen
    filesystem/fsockopen
}}
