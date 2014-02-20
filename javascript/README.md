# Javascript

## Live edit

Use this to execute code after a component has been saved:

	if (typeof isInEditMode != 'undefined') {
		parent.Orange.Events.attach('component_saved', function (p) {
			// p => { id, data, type, component, altered }
		});
	}

Note that Snowfire might reload the page iframe without reloading Snowfire. You need to handle this in your script to not attach multiple event handlers, if that is not intended.