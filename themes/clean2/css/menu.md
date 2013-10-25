Menu modifications
==================

This is a collection of nifty code snippets to modify your Snowfire website. Snippets are sorted by themes.


Right aligned menu
------------------
```css
.top-bar {
	float: right;
}
```


Right aligned menu on the logo row
----------------------------------

```css
float: right;
margin-top: -65px !important;
height: 35px;
```


Active menu item and mouseover
------------------------------

```css
.top-bar .top-bar-section ul > li.activeRoot a,
.top-bar .top-bar-section ul > li a:hover {
	background: #4fccdd !important;
	border-radius: 3px 3px 0 0;
	color: #fff;
}
```


Solid menu background
---------------------

```css
#top {
	border: 0;
	height: 126px;
}
#top-nav.row {
	height: 36px;
	max-width: 100%;
	width: 100%;
	background: #4fccdd;
	margin: 0;
}
	#top-nav .z_columns {
		max-width: 72.5em;
		margin: 0 auto;
		float: none;
		height: 36px;
	}
	
.top-bar .top-bar-section ul > li a {
	background: #4fccdd !important;
}

.top-bar .top-bar-section ul > li.activeRoot a,
.top-bar .top-bar-section ul > li a:hover {
	background: #77E9F8 !important;
	border-radius: 0;
	color: #16646F;
}
```