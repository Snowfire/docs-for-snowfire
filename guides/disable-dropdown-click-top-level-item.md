# Disable click on top level navigation for dropdown

This js code will make it impossible to click on a menu item which has a dropdown. The user will have to click on a sub item.

```javascript
$('.has_dropdown > a').click(function() {
	return false;
}).css('cursor', 'default');
```
