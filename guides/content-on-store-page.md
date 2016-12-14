# Add content above products on store page

Add this to your javascript file

```js
$(document).ready( function () {
	var heading = 'Heading'
	var text = 'A text below the heading';
	var html = '<div class="intro-content" style=""><div class="row"><div class="col-md-6 col-md-offset-3 text-center shop-intro"><h1>' + heading + '</h1><p>' + text + '</p></div></div></div>';
   	$('.products').prepend($(html));
});
```
