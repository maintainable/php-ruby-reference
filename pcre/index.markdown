# Regular Expression Functions

PHP implements both POSIX and Perl-compatible regular expressions. The
Perl-compatible regexp functions (which includes all the `preg_*`
functions) is the preferred library for most developers since it has many
features not available in POSIX, and is binary safe.

Ruby uses Perl-compatible regular expressions, so if you're familiar with the
`preg_*` functions in PHP, you're already well on your way to
learning regular expressions in Ruby. Regular expressions are a complex topic,
so we won't be covering regular expression basics, but will instead focus on
translating existing knowledge of Perl-compatible PHP functions to Ruby.

## Regular Expressions in Ruby

We use regular expression patterns in PHP by passing a string argument to
various functions. Ruby treats regular expressions differently. Instead of
specifying the pattern within a string, they are objects just like everything
else in Ruby.


{{code:php
    $myRegexp = '/[a-z0-9]+\s/mi';
    print gettype($myRegexp); 
    // => string
}}


{{code:ruby
    my_regexp = /[a-z0-9]+\s/mi
    p my_regexp.class
    # => Regexp
}}

We can create regular expressions in Ruby using two different literal
syntaxes.

The most common is by enclosing the pattern in forward-slashes, but we can
also use an alternate `%r{}` syntax. We usually use
`%r{}` when the pattern contains a lot of forward-slashes (such as
a filepath). Regular expressions can also be explicitly instantiated using the
Regexp class.


{{code:ruby
    /[a-z0-9]+\s/mi
    %r{/path/to/gif\.gif}mi
    Regexp.new("[a-z0-9]+\s", Regexp::IGNORECASE | Regexp::MULTILINE)
}}

## Regular Expressions in Rails

Rails uses regular expressions in various places to specify patterns. When we
are matching a route in Rails, we can use them to assign a requirement that a
route component must match:


{{code:rails
    ActionController::Routing::Routes.draw do |map|
      map.connect 'teams/:team_id/players/:action/:id, :team_id => /\d+/
    end
}}

We can also use regular expressions in our models when we validate the format
of data. We pass a regexp to the `:with` option of `validates_format_of`:


{{code:rails
    class Image < ActiveRecord::Base
      validates_format_of :url, :with => /\.(gif|jpg)/i, 
                          :message => "must be a GIF or JPG" 
    end
}}

When we are testing controller code, the `assert_select` method will accept a
regular expression to match response data according to the given pattern.


{{code:rails
    class HomepageControllerTest < ActionController::TestCase
      def test_greeting
        get :index
        assert_select 'div.greeting', /Welcome [a-z0-9-_]+/
      end
    end
}}
