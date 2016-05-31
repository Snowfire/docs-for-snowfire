# snippet-containers.xml

This file defines which page layouts the user is able to select within Snowfire.

For example, the original theme has three main page types:

* One Column (one_column)
* Blog (blog)
* Shop (shop)

If you create a new layout in the code editor a file called snippet-containers.xml will appear with your new layout.

Example:

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippetContainers>
  <container>
    <id>wide</id>
    <name>Wide</name>
  </container>
</snippetContainers>
```

If you want to hide the default `one_column`, add the following code:


```xml
<!-- Hide one column layout -->
<container hidden="true">
  <id>one_column</id>
  <name>One column</name>
</container>
```

### Theme styles

If you are using a theme which has different styles, you can choose to only show a layout for a specific style like this:

```xml
<!-- Only for evolve -->
<container styles="evolve">
  <id>my_layout</id>
  <name>My Layout</name>
</container>
```

This will only show my layout if you are using Inspire with the Evolve style. The styles attribute allowed multiple styles if you comma separate them. `evolve,movement`
