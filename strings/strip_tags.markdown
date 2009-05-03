# strip_tags

{{notice:
    This function's solution will only work within the context of the Rails
    framework.
}}

Rails has a series of helpers to help sanitize output. These are all in
ActionView's `ActionView::Helpers::SanitizeHelper` module. We can strip tags
from text in Rails using the `sanitize` method which takes a list of optional
`tags` or `attributes` as a whitelist.

{{code:php
    $content = "<strong>Test</strong> some <em>tags<em>";
    $result = strip_tags($content, '<em>');
    var_export($result);
    // => 'Test some <em>tags<em>'
}}

{{code:rails
    # in app/views/posts/index.html.erb
    <% @text = "<strong>Test</strong> some <em>tags<em>" %>
    <%= sanitize(@text, :tags => %w(em), :attributes => %w(style)) %>
    # => "Test some <em>tags<em>"
}}

Rails also has helpers to `sanitize_css`, `strip_tags`, `strip_links`


{{related:
    strings/htmlspecialchars
}}
