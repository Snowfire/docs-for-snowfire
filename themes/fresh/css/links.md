Links
=====

By default, all links will get an underline in the colour from the design mode. On mouseover the text colour will change to the same colour as the underline.

```css
/* Active */
#clean .snippet_area_main a, 
#clean .blog a, 
#clean #sidebar .snippet_area_sidebar a, 
#clean #sidebar .side-nav-clean a:hover {
	border-color: #A033AF
}

/* Mouseover */
.top-bar ul > li.active a, 
.top-bar ul > li:focus a, 
.top-bar .top-bar-section ul > li.activeRoot a, 
.top-bar .top-bar-section ul > li a:hover, 
#clean .snippet_area_main .side-nav-clean a:hover, 
#clean #sidebar .snippet_area_sidebar a:hover, 
#clean .snippet_area_main a:hover, 
#clean .blog a:hover {
	color: #A033AF
}
```


Buttons
-------

Change button design

```css
/* Active */
.column.cta_button a, 
.column.cta_button_synced a {
	color: red !important;
}

/* Mouseover */
.column.cta_button a:hover, 
.column.cta_button_synced a:hover {
	color: green !important;
}
```