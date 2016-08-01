# Events

## Usage in Snowfire

A theme is require to have `event.tpl` and `events.xml` to work with Events. 

* [Layout XML files example](xml-files.md)
* [Categories](categories.md)
* [List of events](list.md)

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

### Images

These settings will make sure the Flake event admin UI asks for three images and resize/crops them accordingly.

* `name` - this value must be unique and only small characters (A-Z) allowed
* `title` - visible for the user inside the UI
* `width/height` - in px

```
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    [..]

    <template_config>
        <settings>
        
            [..]

            <images>
                <image name="primary" title="Primary image">
                    <width>1920</width>
                    <height>650</height>
                </image>
            </images>

        </settings>
    </template_config>

</snippet_container>
```

### Short description

We support two description fields. The short description is hidden by default. To enable it, add `shortDescription` in `settings` like this:

```
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    [..]

    <template_config>
        <settings>
        
            [..]

            <shortDescription length="140"></shortDescription>

        </settings>
    </template_config>

</snippet_container>
```

The short description field will now show up when you edit an event. It will be limited to `140` characters. But it is up to you to choose a limit that fits your layout. We recommend using the short description when you list many events on a single page. 


### Ribbon

You can use the ribbon field to add things like "SALE" or "SOLD OUT". Users are free to enter whatever they want in this field, and it is up to you how it looks. Add `<ribbon></ribbon>` in `event.xml` in the `settings` tag exactly as `shortDescription`. 


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
