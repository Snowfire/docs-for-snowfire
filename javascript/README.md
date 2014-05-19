# Javascript

## Live edit

### Condition if inside or outside of Live Edit

```javascript
if (typeof isInEditMode != 'undefined') {
    alert('I won\'t popup inside edit mode');
}
```


### Code execution

Use this to execute code after a component has been saved:

```javascript
if (typeof isInEditMode != 'undefined') {
	parent.Orange.Events.attach('component_saved', function (p) {
		// p => { id, data, type, component, altered }
	});
}
```

Note that Snowfire might reload the page iframe without reloading Snowfire. You need to handle this in your script to not attach multiple event handlers, if that is not intended.
