Text with form snippet
======================

Creates a snippet with a text (for headline, description of form etc) and then a form

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>Form with text</name>
    <html>
        <![CDATA[
			{ com_wysiwyg ( id:'{{ component_id }}', description:'Enter text here' ) }
			{ com_form(id:'{{ component_id }}', description:'Choose form', disableHeading:'true') }
        ]]>
    </html>
</snippet>