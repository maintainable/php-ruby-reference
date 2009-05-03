# parse_ini_file

We use the `parse_ini_file` function in PHP to read Windows-style INI
configuration files, like `php.ini`. Given this INI file in
`/path/to/foobar.ini`:

{{code:ini
    [foo]
    bar=baz
}}

We can then parse the file easily using `parse_ini_file`:

{{code:php
    $conf = parse_ini_file('/path/to/foobar.ini', true);
    print $conf['foo']['bar'];

    //=> "baz"
}}

It's surprisingly difficult to parse an INI file in Ruby because there's no
support for it in the Ruby Standard Library and also no projects on RubyForge
to help.

We found [this snippet](http://snippets.dzone.com/posts/show/4918) on DZone
that implements INI handling in Ruby. Using it is similar to
`parse_ini_file`:

{{code:ruby
    conf = Ini.new('/path/to/foobar.ini')
    p conf['foo']['bar']

    #=> "baz"
}}

The absence of INI support in Ruby is most likely due to its culture. PHP
users are very accustomed to working with INI files like `php.ini`. Rubyists
tend to favor [YAML](http://www.yaml.org/), which is the format of
Rails' database configuration file (`database.yml`).

For more information on YAML in both Ruby and PHP, see our article
[PHP, Meet YAML](http://railsforphp.com/2008/01/08/php-meet-yaml/).
