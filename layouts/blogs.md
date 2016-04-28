## Blogs

Inspire comes with a couple of different blog layouts. Only one is visible by default.

## Change blog layout

If you want to try all different blog layouts. Open `snippet-containers.xml` in the code editor (create a new layout called test if you don't see it). 

Add the following containers to it:

```xml
<container>
  <id>blog</id>
  <name>Blog - large image</name>
</container>
<container>
  <id>simple_blog</id>
  <name>Blog - normal image </name>
</container>
<container>
  <id>vivid_blog</id>
  <name>Blog - grid</name>
</container>
```

When you know which layout you want. Append `hidden="true"` to the others. Like this:

```xml
<container hidden="true">
  <id>vivid_blog</id>
  <name>Blog - grid</name>
</container>
```
