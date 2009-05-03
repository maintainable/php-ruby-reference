# wordwrap

{{notice:
    This function's solution will only work within the context of the Rails
    framework.
}}

There is no native wordwrap function in Ruby, but we can achieve similar
results with the `String.gsub` method.

{{code:php
    $string = "The quick brown fox jumped over the lazy dog.";
    $result = wordwrap($string, 20, "<br />\n");
    var_export($result);
    // => "The quick brown fox<br />\njumped over the lazy<br />\ndog."
}}

{{code:ruby
    string = "The quick brown fox jumped over the lazy dog."
    string.gsub(/(\w.{1,20})(\s+)/s, "\\1<br />\n")
    # => "The quick brown fox<br />\njumped over the lazy<br />\ndog."
}}

Rails includes a built-in helper method to perform word wrap operations in
your views.

{{code:rails
    <%= word_wrap "The quick brown fox jumped over the lazy dog.", 20 %>
}}

Produces:

{{code:html
    The quick brown fox
    jumped over the lazy
    dog.
}}


{{related:
    strings/nl2br
    strings/chunk_split
}}
