# Layouts


## Page name

Displays the current page name.

	{ var_pageName }

Example:

	Welcome to this page!


	{ var_pageNameLowerCase }

Example:

	welcometothispage


## Page identifier

A unique numeric identifier.

	{ var_pageId }

Example:

	5


## Date

Displays the publish date of a page (change publish date in page settings):

	{ var_publishDate }

Example:

	2010-08-24

For formatting options, see `fnc_publishDate`.


### `fnc_publishDate`

	{ fnc_publishDate ( format:'%Y-%m-%d' ) }

#### Output

	2010-10-18

#### Parameters

* `format` - [Date format](dates.md).


## Paths

This is how you access files uploaded to the various directories via FTP.

### Images


	{ var_images }


Example usage:

```html
<img src="{ var_images }/logo.jpg" alt="My Logo" />
```


### Javascripts

	{ var_javascripts }

Example usage:

```html
<script type="text/javascript" src="{ var_javascripts }/script.js"></script>
```


### CSS

	{ var_styles }

Example usage:

```html
<link rel="stylesheet" href="{ var_styles }/style.css" type="text/css" />
```


### `fnc_resource`

	{ fnc_resource ( file:'logotype.png', alt:'Logotype' ) }

#### Output

```html
<img src="/accounts/1234/images/logotype.png?t=2010-10-05-21-36-04" alt="Logotype" />
```

#### Parameters

* `file` - The image file to load. The path should be relative to `/images` directory in the account FTP.
* `alt` - Set the `alt` attribute of the image.


## URLs

### Site

	{ var_site }

Example:

	http://my-site.snowfireapp.com


### Current URL

	{ var_url }

Example:

	http://my-site.snowfireapp.com/my-page/sub-page


	{ var_urlNoDomain }

Example:

	/my-page/sub-page


	{ var_pageUrl }

This is the base page URL, with no pagination data appended.

Example:

	my-page/sub-page


	{ var_pageFullUrl }

This is the full base page URL, with no pagination data appended.

Example:

	http://my-site.snowfireapp.com/my-page/sub-page


## Tags

### `fnc_hasTag`

```html
<div class="
	{ fnc_hasTag ( tags:'foo,bar', after:'-style' ) }
">
</div>
```

Adds a class named `foo-style` or `bar-style` if the current page is tagged with those tags.


#### Full featured example

	{ fnc_hasTag ( tags:'foo, bar', after:'[after]', before:'[before]', separator:'[separator]' ) }

Generates the following, if both `tags` foo and `bar` are set.

	[before]foo[after][separator][before]bar[after]


#### returnOnTrue/False example

	{ fnc_hasTag ( tags:'foo', returnOnTrue:'exists' ) }

Generates the following, if tag `foo` is set.

	exists


	{ fnc_hasTag ( tags:'foo', returnOnFalse:'missing' ) }

Generates the following, if tag `foo` is not set.

	missing


#### Wildcards

It is possible to write dynamic tag selectors, using wildcards. To match the tags `color-blue` and `color-red` you can either write `tags:'color-blue, color-red'`, or with wildcards `tags:'color-*'`.


## Partials

	{{ partial: file.tpl }}

Loads a file from `studio/partials/`.


## Edit mode

	{ fnc_editMode ( active:'edit_mode' ) }

In edit mode (Snowfire), this will output

	edit_mode

otherwise nothing.
