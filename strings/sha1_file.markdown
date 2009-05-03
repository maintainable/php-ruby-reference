# sha1_file

There are generally two different ways in Ruby to generate a cryptographic
hash of a file. The first and easiest way is to use `File.read` to read the
entire file contents into memory. We can then use the same `SHA1.hexdigest`
method on the contents to generate the hash.

{{code:php
    print sha1_file("my_file.jpg");
    // => 5de1a26c24b0d176c6cafd11bf1f03017bcc767b
}}

{{code:ruby
    require "digest"

    print Digest::SHA1.hexdigest(File.read("my_file.jpg"))
    # => 5de1a26c24b0d176c6cafd11bf1f03017bcc767b
}}

The code above works for many cases but for larger files, there's a risk of
consuming large amounts of memory. For these cases, we can initialize a new
digest with `Digest::SHA1.new` and then read the file in smaller chunks,
incrementally building the digest with `SHA1#update`.

{{code:ruby
    require "digest"

    digest = Digest::SHA1.new
    File.open("my_file.jpg", "r") do |f|
      digest.update f.read(8192) until f.eof
    end

    print digest.hexdigest
    # => 5de1a26c24b0d176c6cafd11bf1f03017bcc767b
}}


{{related:
    strings/crc32
    strings/sha1
    strings/md5
    strings/md5_file
}}
