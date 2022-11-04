# Minify

A simple package to minify CSS/SCSS and Javascript on the fly without the need of tools like Laravel Vite, Mix or Webpack.
It combines all stylesheet files or javascript files into a single, minified file with simple but effective cachebusting with filemtime().

Version 2 is a completely new package ([forked version 2](https://github.com/nickdekruijk/minify)) and ([version 1](https://github.com/nickdekruijk/minify1)) using  [scssphp/scssphp](https://github.com/scssphp/scssphp) and [tedivm/jshrink](https://github.com/tedivm/jshrink). Because minify  now replaces natxet/cssmin with scssphp it can now compile SASS/SCSS code too!

## Installation

Begin by installing this package with composer.

`composer require 0x1881/minify`

### Laravel installation

Publish the config file if the defaults doesn't suite your needs:

```php artisan vendor:publish --provider="C4N\Minify\ServiceProvider"```

### Stylesheet

```html
// app/views/hello.blade.php
<html>
    <head>
        ...
        {!! Minify::stylesheet(['lightbox.css', 'fonts.css', 'styles.css']) !!}
    </head>
    ...
</html>

```

### Javascript

```html
// app/views/hello.blade.php

<html>
    <body>
        ...
        {!! Minify::javascript(['lazyload.min.js', 'scripts.js']) !!}
        <!-- Or: -->
        {!! Minify::javascript(['https://cdn.jsdelivr.net/npm/vanilla-lazyload@12.4.0/dist/lazyload.min.js', 'scripts.js') !!}
    </body>
</html>
```

### Config
See the config file at `/config/minify.php`

### Thanks
@nickdekruijk
