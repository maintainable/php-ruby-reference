# htmlentities

{{notice:
    This function's solution will only work within the context of the Rails
    framework.
}}

Escaping a string to be safe for output in HTML is done using the
`CGI.escapeHTML` class method. Rails provides the `h` helper method as a
convenient shortcut to this method within our views.

{{code:php
    $result = htmlentities('test "escaping" <characters>'); 
    var_export($result);
    // => "test &quot;escaping&quot; &lt;characters&gt;"
}}

{{code:ruby
    require 'cgi'

    p CGI.escapeHTML('test "escaping" <characters>')
    # => "test &quot;escaping&quot; &lt;characters&gt;"
}}

To convert unicode characters to HTML entities in Ruby, we need to loop
through the string characters using `String#unpack`.

{{code:ruby
    str = "Résumé"
    str.unpack("U*").collect {|s| (s > 127 ? "&##{s};" : s.chr) }.join("")
    p str
    # => "R&#233;sum&#233;"
}}

{{code:rails
    # In app/controllers/users_controller.rb
    class UsersController < ActionController::Base
      def show
        @user = User.find(params[:id])
      end
    end

    # In app/views/users/show.html.erb
    <p><%= h(@user.username) %></p>

    # or the equivalent and often preferable
    <p><%=h @user.username %></p>
}}

{{related:
    strings/html_entity_decode
    strings/nl2br
    strings/urlencode
    strings/get_html_translation_table
    strings/html_entity_decode
}}
