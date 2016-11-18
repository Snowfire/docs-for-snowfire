# Snowfire Code Editor

## CSS / SCSS

All CSS inside Snowfire is transpiled with SCSS. Feel free to write CSS, or take advantage of the more advanced features of SCSS 
such as indentation and variables.

### Using multiple files

The only file that is included on your website is `style.css`. If you create other style files you'll need to import them in 
the style file like this:

```scss
@import 'menu'

body {
  background: orange;
}
```

_If you have a style called `_menu`_


## JavaScript

All JS are transpiled with Browserify to make it possible to have functions in different files.

### Using multiple files

Create a JS file called `name` with the following contents:

```javascript
module.exports = function(name) {
    return 'Hello ' + name + '!';
};
```

Now include it in the `app` file with

```javascript
var name = require('./name');
var welcomePhrase = name('Emil');
alert(welcomePhrase);
```

## Partials

If you create a partial called `extra`, include it in a template file like this:

```html
{{ partial: extra.tpl }}
```
