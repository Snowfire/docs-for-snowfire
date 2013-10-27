My first snippet
================

This guide will show you how to create a custom snippet (referred to as Content Block inside the app). As an example, we will make it possible for our users to add round images to the page. 

1. The code editor
------------------

Open the code editor by going to the developer toolbar, located in the top left corner (make sure you have enabled developer tools first). Ignore everything in the drop down and just go to the code editor in the bottom (Hint: right click to open it in a new browser tab).

By default the editor will open the global CSS file which might be empty. You can't open existing CSS files since they are managed and updated by the Snowfire Team. Instead you have the ability to create new rules and override existing to make your own style, but about that later.



2. Create a snippet
-------------------
In the right toolbar you have a heading called Snippets and below it a Create new button. Hit it! Name your snippet with small letters and underscore instead of space. 

Good examples:
* large_image
* form_with_heading
* gallery

I'll create one named round_image. The editor will create the file and open it with some example content. The interesting part is row 5. Remove it and replace it with the following:

```html
<h1>A round image!</h1>
{ com_image ( id:'{{ component_id_0 }}', description:'Image', maxHeight:'100', maxWidth:'100', crop:'true' ) }
````

Click save. (Hint: Save quickly by hitting CMD+S)



3. Write CSS
------------

Snowfire generates HTML to make it possible for a user to add/move snippets on a page. Each snippet will be wrapped in a div element with its name as class. That makes is super simple to style.

Open the global CSS by hitting the word global under the CSS heading in the right toolbar. Now paste the following code:

```css
.column.round_image img {
	border-radius: 100px;
}
```

Save and go back to Create. Now click the Add button and your new snippet should appear. 



Bonus
-----

Hey, what about that annoying heading. How can I make it editable for my users? Good question. Open the snippet round_image in the code editor and replace the following code:

```html
<h1>A round image!</h1>
```

with this:

```html
{ com_singlerow ( id:'{{ component_id_1 }}', description:'Heading', htmlElement:'h1' ) }
```
