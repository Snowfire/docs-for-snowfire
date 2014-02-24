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
.top-bar {
	float: right;
	margin-top: -65px !important;
	height: 35px;
}
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
@media only screen and (max-width: 941px) {
	.top-bar .top-bar-section ul > li a {
    	background: #000 !important;
	}
}

.top-bar .top-bar-section ul > li.activeRoot a,
.top-bar .top-bar-section ul > li a:hover {
    background: #77E9F8 !important;
    border-radius: 0;
    color: #16646F;
}
```


Change responsive menu color
----------------------------

```css
@media only screen and (max-width: 940px) {
	.top-bar, 
	.top-bar.expanded .title-area {
		background: green;
	}
	
	.top-bar {
		margin-top: 0;	
	}
	
	#clean .top-bar ul > li a:hover, 
	#clean .top-bar ul > li.active a, 
	#clean .top-bar ul > li:focus a,
	#clean .top-bar .top-bar-section ul > li.activeRoot a,
	#clean .top-bar .top-bar-section ul > li.activeRoot a:hover,
	#clean .top-bar .top-bar-section ul > li a,
	#clean .top-bar .top-bar-section ul > li a:hover,
	#clean .top-bar ul > li a,
	#clean .top-bar ul > li a:hover, 
	#clean .top-bar ul > li.active a {
		background: green !important;
		color: #fff !important;
	}
}
```
