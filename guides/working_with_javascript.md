Working with javascript in Snowfire
===================================

Exlude JS from edit mode
------------------------

Sometimes you want to run JS for visitors, but not when your users are logged in to Snowfire and are editing a page. Use the following condition to check if a JS is executed within Snowfire:

```javascript
	if(typeof(isInEditMode) == 'undefined') {
		alert("Hi, I won't pop up inside Live edit");
	}
```