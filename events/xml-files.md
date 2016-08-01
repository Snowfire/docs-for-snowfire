## events.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    [..]

    <template_config>
    	<settings>
    		<contentType>events</contentType>
              <children>
                  <layouts allowNewLayout="true" snippetContainer="event" />
                  <contentType>event</contentType>
                  <noAddToMenu>true</noAddToMenu>
                  <notEmpty>true</notEmpty>
              </children>
    	</settings>
    </template_config>
    
</snippet_container>
```

## event.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    [..]

    <template_config>
        <settings>
            <contentType>event</contentType>

            <images>
                <image name="primary" title="Primary image">
                    <height>650</height>
                    <width>1920</width>
                </image>
                <image name="secondary" title="Secondary image">
                    <width>200</width>
                </image>
                <image name="grid" title="Grid image">
                    <height>100</height>
                    <width>100</width>
                </image>
            </images>
            
            <shortDescription length="140"></shortDescription>

        </settings>
    </template_config>

</snippet_container>
```

### Images height/width

We always recommend to specify a width and height for an image. This will make it simple to crop the image for different views (single event, event list). 

If you don't provide `height` (as the secondary image in the example above) we will set the image width to `200` and then resize the image proportionally. 
