# Activate the template engine

If you want to use the template engine in a layout. Please open its `.xml` file and add 
`<template_engine>active</template_engine>` 

It should then look something like this: 

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

	<options>
		<component_id_offset>1000</component_id_offset>
		<template_engine>active</template_engine>
	</options>
	
	[..]
```

---

If you are working with a snippet, add the same parameter like this:

```
<?xml version="1.0" encoding="utf-8"?>
<snippet>
	<name>My snippet</name>
	<template_engine>active</template_engine>

	[..]
```

