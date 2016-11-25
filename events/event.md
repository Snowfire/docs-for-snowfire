# Event

Display a single event in your `event` template

```html
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

## Which data do I have access to?

Write ```{{ flakeData }}``` somewhere inside the `code` parameter in liquid2 to output all data. 

## Use event image as CSS background image

```html
<div style="background-image:url({{ images.primary.src_escaped }})"></div>
```

## Dates

See [the php documentation](http://php.net/manual/en/function.strftime.php) for how to format the date with different %e %B

```
{{ starts_at | stringToDateFormat:"%e %B %Y" }}
```