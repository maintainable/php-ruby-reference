# addslashes

{{notice:
    This function's solution will only work within the context of the Rails
    framework.
}}

This should NOT be used to escape values being inserted into
the database. This function is generally deprecated in favor of either the
`mysql_real_escape_string` function or bind variables in PHP.

{{code:php
    // don't do this!
    $name = addslashes("O'malley");
    mysql_query("SELECT * FROM users WHERE name='$name'");
}}

To escape variables in Rails, we'll use replacement variables. 

{{code:rails
    name = "O'malley"
    User.find(:all, :conditions => ["name = ?", name])
}}

If you need to escape characters in a string (but are not using this to escape
data for the database) this can be done in Ruby with substitution on the
(`'`), (`"`), and (`\0`) characters using `String#gsub`.

{{code:php
    $string = addslashes("I can't imagine \"that\"!\0");
    var_export($string);
    // => 'I can\\\'t imagine \\"that\\"!\\0'
}}

{{code:ruby
    p "I can't imagine \"that\"!\0".gsub(/('|"|\0)/, "\\\\\\1")
    # => "I can\\'t imagine \\\"that\\\"!\\\000"
}}

Note that PHP's `var_export` dumps with apostrophes ("single quotes") while
Ruby's `p` dumps with quotes. Despite this difference in appearance, the
results are equivalent.


{{related:
    strings/stripslashes      
    strings/stripcslaches     
    strings/addcslashes       
    strings/htmlspecialchars  
    strings/quotemeta         
    strings/get_magic_quotes_gpc
}}
