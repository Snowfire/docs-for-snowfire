```javascript
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>Top heading</name>
    <html><![CDATA[

            <div class="content">
                <div class="intro">
                    { com_singlerow(
                        id: '{{ component_id_1 }}',
                        description: 'Headline',
                        htmlElement:'h1'
                    ) }

                    { com_wysiwyg(
                        id: '{{ component_id_2 }}',
                        description: 'Subheading'
                    ) }
                </div>
            </div>

	]]></html>
</snippet>
```
