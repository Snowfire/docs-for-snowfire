A full width section
====================

Create a snippet named "my_section" and paste the following code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>my_section</name>
    <html><![CDATA[

  		<div class="inner">
  			{ com_singlerow(id:'{{ component_id_0 }}', description: 'Title', htmlElement:'h1') }
  			{ com_wysiwyg(id:'{{ component_id_1 }}', description: 'Text') }
  		</div>

	]]></html>
</snippet>
```


And add the following CSS code to the global CSS:

```css
/*******************************************
  START CB: MY SECTION
*******************************************/

.columns.my_section {
	max-width: 100%;
	padding: 50px 0;
}

	.columns.my_section .inner {
		max-width: 63em;
		margin: 0 auto;

		padding-left: 0.9375em;
		padding-right: 0.9375em;
	}


/*******************************************
    END CB: MY SECTION
*******************************************/
````

Explanation
-----------

We start by resetting the .columns width to 100% and then create an inner div which aligns its content with the other default content blocks.
