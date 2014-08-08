# Example of partial top

When creating a layout in Original, you'll find this code:

```javascript
{{ partial: top.tpl }}
```

This can be replace by the following code if you want to modify it:

```html
<header id="page_top">

	<div class="row">
		<div class="large-12 z_columns">
			<div class="tbl">
				<div id="logo_wrapper">
					<div id="logo">{ fnc_designstudio ( part:'header' ) }</div>
				</div>
			</div>
		</div>
	</div>

	<div class="navbar">
	    <div class="row">
	        <div class="large-12 z_columns">
	            <nav id="menu" class="nav-collapse cf">
                    { com_menu (
	                    id: '1',
	                    description: 'Menu',
	                    syncId: '1',
	                    childrenLevels: '1',
	                    hasChildrenClass: 'has_dropdown',
	                    itemHtml: '<li %class%><a href="%link%">%name%</a></li>',
	                    childItemHtml: '<li %class%><a href="%link%">%name%</a></li>'
	                ) }
                </nav>
            </div>
        </div>
    </div>


</header>
```
