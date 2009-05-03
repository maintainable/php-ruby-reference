# md5_file

There are generally two different ways in Ruby to generate a cryptographic
hash of a file. The first and easiest way is to use `File.read` to read the
entire file contents into memory. We can then use the same `MD5.hexdigest`
method on the contents to generate the hash.

{{code:php
    print md5_file("my_file.jpg");
    // => 14b6a00b1a4eb40542cfecdc4d64940d
}}

{{code:ruby
    require "digest"

    print Digest::MD5.hexdigest(File.read("my_file.jpg"))
    # => 14b6a00b1a4eb40542cfecdc4d64940d
}}

The code above works for many cases but for larger files, there's a risk of
consuming large amounts of memory. For these cases, we can initialize a new
digest with `Digest::MD5.new` and then read the file in smaller chunks,
incrementally building the digest with `MD5#update`.

{{code:ruby
    require "digest"

    digest = Digest::MD5.new
    File.open("my_file.jpg", "r") do |f|
      digest.update f.read(8192) until f.eof
    end

    print digest.hexdigest
    # => 14b6a00b1a4eb40542cfecdc4d64940d
}}


{{related:
    strings/crc32
    strings/md5 
    strings/sha1_file
    strings/sha1
}}
