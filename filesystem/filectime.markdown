# filectime

To get the inode change time of a file in PHP, we use `filectime`. It returns
an integer with a timestamp (seconds since Unix epoch).

{{code:php
    $timestamp = filectime('/path/to/foobar');
    print $timestamp;

    //=> 1205621108
}}

Ruby's `File.ctime` method accomplishes the same task, only it returns an
instance of `Time` instead of an integer:

{{code:ruby
    time = File.ctime('/path/to/foobar')
    p time

    #=> Sat Mar 15 15:45:08 -0700 2008
}}

If you then need the timestamp (seconds since Unix epoch) as an integer, use
the `Time#to_i` method:

{{code:ruby
    timestamp = time.to_i
    p timestamp

    #=> 1205621108
}}


{{related:
    filesystem/filemtime
}}
