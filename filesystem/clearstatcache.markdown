# clearstatcache

In both PHP and Ruby, various file operations result in the interpreter
calling down to the underlying operating system's `stat` function to query
information about the filesystem.

The architecture of PHP is built around the notion of a PHP program living
only for the lifetime of a single HTTP request. With this assumption, various
performance optimizations can be made. One of these optimizations is that when
you use PHP filesystem functions that result in `stat` calls to the OS, PHP
will cache the result. If another `stat` on the same file is needed during the
request, PHP will pull the information from its cache, avoiding the expense of
another call down to the operating system.

This is usually what you want, but sometimes even within a single request, a
PHP script needs to ensure the `stat` of a file is not stale. The
`clearstatcache` function is used to clear the cache for this use case.

## Ruby doesn't stat cache

Ruby, being a more general purpose language than PHP, is not built around the
notion of a HTTP request and as such does not have some optimizations like
this one. Calls to methods like `File.exist?` will result in a `stat` call
every time. This is true even with the Rails framework, with one exception
noted below.

As a consequence, Ruby can be less performant in this regard and does not have
an equivalent of PHP's `clearstatecache` function.

## Rails sometimes stat caches

The two most expensive filesystem operations that Rails performs are loading
your classes (primarily models and controllers) and rendering your views.

In the `production` environment mode, your classes are only loaded once. This
means that a `stat` is only performed once, when the file is loaded for the
first time. For subsequent requests, the file is not reloaded from the
filesystem, and thus the `stat` is not performed.

In Rails versions prior to 2.0.2, rendering ActionView templates resulted in
`stat` calls on those files on every request. However, Rails 2.0.2 added a new
default in `config/environments/production.rb`:

{{code:rails
    config.action_view.cache_template_loading = true
}}

This results in `stat` calls on the views occuring only once, just like models
and controllers. For all other filesystem operations within the context of
Rails, there is no `stat` cache and the behavior is the same as standalone
Ruby.
