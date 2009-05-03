# pathinfo

The `pathinfo` function in PHP returns an associative array with information
about a file path. The array should contain the keys `dirname`, `basename`,
`extension`, and `filename`.

{{code:php
    $pathinfo = pathinfo('/path/to/foo.bar');
    var_export($pathinfo);

    //=> array (
    //     'dirname'   => '/path/to',
    //     'basename'  => 'foo.bar',
    //     'extension' => 'bar',
    //     'filename'  => 'foo',
    //   )
}}

Ruby does not have an equivalent method to `pathinfo`. However, the `File`
class contains individual methods that can return the same information. It is
preferable to use these individual methods: `File.dirname`, `File.basename`,
and `File.extname`.

If a `pathinfo` method is convenient, one approach would be to take advantage
of Ruby's open classes to monkeypath a new method onto the `File` class:

{{code:ruby
    class File
      def self.pathinfo(path)
        { :basename  => basename(path),
          :dirname   => dirname(path),
          :extension => extname(path),
          :filename  => basename(path, extname(path))
        }
      end
    end
}}

You could then call `File.pathinfo`:

{{code:ruby
    pathinfo = File.pathinfo('/path/to/foo.bar')
    p pathinfo

    #=> { :basename  => "foo.bar",
    #     :dirname   => "/path/to/foo.bar", 
    #     :extension => ".bar"
    #     :filename  => "foo" }
}}

The snippet above is roughly equivalent but has a minor difference from the
PHP version. The `File.extname` method returns the leading period (`.bar`) but
the `extension` element returned by PHP's `pathinfo` does not.


{{related:                
  filesystem/dirname      
  filesystem/basename     
  filesystem/parse_url    
  filesystem/realpath
}}
