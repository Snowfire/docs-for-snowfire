# Level 2 – Use the power of JavaScript

Firecode gives you a single JS file. We've included jQuery and Browserify by default.

Lets fire up the app.js file and enter the following code

```js
if (typeof(isInEditMode) == 'undefined') {
	alert('Hello World')
}
```

This will create a popup which only is displayed when a user is in edit mode

## Move your functions into their own files

Create a new JS file called `name`. 

```javascript
module.exports = function(name) {
    return 'Hello ' + name + '!';
}
```

Now head back to your `app` file and import it:

```javascript
var name = require('./name');
var welcomePhrase = name('Emil');
alert(welcomePhrase);
```

Cool, right? :)

