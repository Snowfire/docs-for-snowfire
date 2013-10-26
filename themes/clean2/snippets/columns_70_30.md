Contents divided into a 70/30 column
====================================

Create a snippet named "columns_70_30" and paste the following code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>Columns 70 30</name>
    <html><![CDATA[
      <div class="column_left">
        { com_wysiwyg ( id:'{{ component_id }}', description:'Enter text here' ) }
      <div class="both"></div>
      </div>
      <div class="column_right">
        { com_image ( id:'{{ component_id }}', description:'Image') }
        <div class="both"></div>
      </div>
      <div class="both"></div>
  ]]></html>
</snippet>
```


And add the following CSS code to the global CSS:

```css
/*******************************************
  START CB: COLUMNS 70 30  
*******************************************/

.column.columns_70_30 .column_left {
  float: left;
  width: 70%;
  padding-right: 20px;
}

.column.columns_70_30 .column_right {
  float: left;
  width: 30%;
}

.column.columns_70_30 .both {
  clear: both;
}

@media only screen and (max-width: 599px) {
  .column.columns_70_30 .column_left,
  .column.columns_70_30 .column_right {
    width: 100%;
  }
}


/*******************************************
    END CB: COLUMNS 70 30  
*******************************************/
````
