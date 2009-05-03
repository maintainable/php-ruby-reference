# fileatime

To get the last access time of a file in PHP, we use `fileatime`. It returns
an integer with a timestamp (seconds since Unix epoch).

{{code:php
    $timestamp = fileatime('/path/to/foobar');
    print $timestamp;

    //=> 1205621108
}}

Ruby's `File.atime` method accomplishes the same task, only it returns an
instance of `Time` instead of an integer:

{{code:ruby
    time = File.atime('/path/to/foobar')
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
    filesystem/fileinode  
    datetime/date
}}

