# Event images

These settings will make sure the Flake event admin UI asks for three images and resize/crops them accordingly.

* `name` - this value must be unique and only small characters (A-Z) allowed
* `title` - visible for the user inside the UI
* `width/height` - in px

Open `snippet-container.xml` and add the settings like this:

```
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    [..]

    <template_config>
        <settings>
        
            [..]

            <images>
                <image name="primary" title="Primary image">
                    <width>1920</width>
                    <height>650</height>
                </image>
            </images>

        </settings>
    </template_config>

</snippet_container>
```