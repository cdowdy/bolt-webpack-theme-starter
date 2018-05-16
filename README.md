# Bolt CMS Webpack Theme Starter
  
This is a slightly opinionated [Bolt CMS](https://bolt.cm/) starter template using Webpack to build a theme for bolt.  

This includes:  
- webpack
- babel
- node sass
- mini-css-extract-plugin
- postcss-loader
- autoprefixer

It should be used fas a "jumping off point".  

You'll need to make one adjustment to either you ``config.yml`` or your ``config_local.yml`` in order for the webpack version assets to be delivered. That is as follows:  

```yaml  
assets:
   theme:
        json_manifest_path: "/dist/manifest.json"
```  

This allows your assets to be served from the "dist" directory with the hash that webpack creates. 

this in a template:  

```twig
<link rel="stylesheet" href="{{ asset('dist/app.css', 'theme') }}">
```  

will produce:  

```html
<link rel="stylesheet" href="/theme/your_theme/dist/css/app.bbad62558ef19da7e0ca.css">  

```
the hash part comes from the json manifest produced by webpack. 

``theme.yml`` sets the twig template directory to the directory ``twig``. 

- 1 [Bootstrap](https://getbootstrap.com/docs/4.0/getting-started/introduction/#responsive-meta-tag), [HTML5 Boilerplate](https://github.com/h5bp/html5-boilerplate/blob/269f72796fab92bb703520fdc0dca1cbcb7ecc92/src/index.html#L9)
    and a few others recommend ``shring-to-fit=no`` be added to the viewport meta tag. I won't include it since it's an iOS
    specific thing, they provided no data as to why this is needed and who knows how long they'll continue to need it.
