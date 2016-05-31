# Events

## Usage in Snowfire

A theme is require to have `event.tpl` and `events.xml` to work with Events. 

* [Layout XML files example](xml-files.md)
* [Categories](categories.md)
* [List of events](list.md)

### Parameters

These settings will make sure the Flake event admin UI asks for three images and resize/crops them accordingly.

* `name` - this value must be unique and only small characters (A-Z) allowed
* `title` - visible for the user inside the UI
* `width/height` - in px

### Snowfire component 

Display a simple event in `event.tpl`

```php
{ com_liquid2 (
	id: '1',
	description: 'Event',
	selectablePage: 'false',
	flake: 'events/show',
	debug: 'true',
	flakeAdmin: 'events/editFromPage',
	code: '
		
		<h1>{{ title }}</h1>
		<p>{{ description }}</p>
		
		<img src="{{ images.primary.src }}" alt="">
	
		Price: {{ lowest_ticket_price | currency }} <br>
		Location: {{ location.name }}<br>
		
		<br><br>
		
		<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&amp;{{ currentQueryString }}">
			Buy Ticket
		</a>
		
		
		
	'
)}
```

### Buy ticket link in com_liquid2

```html
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&amp;{{ currentQueryString }}">Buy ticket</a>
```
#### Special fees

This is only used on one customer (4good) I think. You have to enable a feature flag to add/edit fees for tickets. If you enable fees, this is how you show them in admin:

```html
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&t=0&m=0&amp;{{ currentQueryString }}">Buy ticket with non member fee</a>
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&c=1&amp;{{ currentQueryString }}">Buy ticket with company fee</a>
```

#### Which data do I have access to?

Write ```{{ flakeData }}``` somewhere inside the code in liquid2 to output all data. 

#### Use event image as CSS background image

```html
<div style="background-image:url({{ images.primary.src_escaped }})"></div>
```

#### Dates

```
{{ starts_at | stringToDateFormat:"%e %B %Y" }}
```

See [the php documentation](http://php.net/manual/en/function.strftime.php) for how to format the date with different %e %B
