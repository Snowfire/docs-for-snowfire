### blog.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    <options>
        <component_id_offset>1000</component_id_offset>
    </options>

    <template_config>
        <settings>
            <children>
                <layouts allowNewLayout="true" snippetContainer="blog_post" />
                <contentType>post</contentType>
                <noAddToMenu>true</noAddToMenu>
                <notEmpty>true</notEmpty>
            </children>
        </settings>
        <childrenRss>
            <item>
                <content type="html-id">article</content>
            </item>
        </childrenRss>
    </template_config>


</snippet_container>
```