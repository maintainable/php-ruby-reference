# disk_free_space

{{notice:
    This function's solution assumes a Unix-like operating system.
}}

The `disk_free_space` function in PHP will return the number of bytes
remaining on the filesystem containing a given directory.

{{code:php
    $bytes = disk_free_space('/');
    print $bytes;

    //=> 1048576
}}

Ruby does not have an equivalent method and the Ruby Standard Library also
does not provide an easy way to get this same information.

## Scraping the output of `df`

On Unix-like systems, the `df` shell command returns this same information.
One solution is to scrape the output of `df` into a form that's easier to use
in Ruby.

{{code:php
    class DiskReporter
      def self.usage(path='/')
        arg = "'#{path.gsub "'", "\\\\'"}'"
        header, stats = `df -P #{arg}`.split(/\n/)

        # sanity check on df posix output
        posix = /Filesystem\s+(\d+)-blocks\s+Used\s+Avail(?:able)*\s+Capacity\s+Mount/
        header_matches = posix.match(header)
        return false unless header_matches

        # split stats and check for expected results length
        stats = stats.split(/\s+/, 6) unless stats.nil?
        return false if stats.nil? || stats.size != 6

        # calculate percent free/used on this filesystem
        percent_used = stats[4].match(/(\d+)%/)[1].to_i
        percent_free = (100 - percent_used)

        {
         :block_size   => header_matches[1].to_i,
         :filesystem   => stats[0],
         :blocks_total => stats[1].to_i,
         :blocks_used  => stats[2].to_i,
         :blocks_avail => stats[3].to_i,
         :percent_used => percent_used,
         :percent_free => percent_free,
         :mounted_on   => stats[5]
        }
      end
    end
}}

When `DiskReporter.usage` is called, it will return a `Hash` containing the
information returned by the `df` command.

{{code:ruby
    require 'diskreporter'

    usage = DiskReporter.usage('/path/to/foo')

    p usage
    #=> {:filesystem=>"/dev/disk0s2", :blocks_total=>194699744, 
    #    :blocks_used=>142675528, :percent_used=>73, 
    #    :blocks_avail=>51512216, :percent_free=>27, 
    #    :mounted_on=>"/", :block_size=>512}

    p usage[:percent_free]
    #=> 27
}}

It's worth noting that the PHP's `disk_free_space` only results in a single
system call, while this solution launches a process with the `df` command.

This is a more expensive operation, making this solution best for command line
scripts and not for during the HTTP request of a Rails application.


{{related:
    filesystem/disk_total_space
    outcontrol/flush
}}
