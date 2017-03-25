# Event

Please see the events documentation on how to enable events. Once you have events up and running, this component 
allows the user to add an event link anywhere on the website.

```html
<sf-event
    id="{{ component_id_0 }}"
    description="Event"
    image="295x295"
>
    <h1>{{ event.title }}</h1>
    <div>
        <img src="{{ event.image }}" />
    </div>
    <a href="{{ event.url }}">View event</a> 
</sf-event>
```

## Parameters

* `image` -  **required**, the width/height of the primary image
* `set-landing-page-url-to-current-page` - optional, please read below about this option

## Event properties

These are available as `{{ event.X }}` inside the tag. Example: `{{ event.title }}`

* `title` - Title of the event
* `image` - The event image in the resolution you have decided in the `image` parameter (please scroll down for more info regarding this image)
* `image_escaped` - The event with escaped characters, use this when you have the image as a css background image
* `images` - All images, use `{{ images.primary.src }}` to access it
* `ticket_url`
* `url`
* `description`
* `starts_at` - Use `{{ event.starts_at | stringToDateFormat:"%e %B %Y" }}` to choose date format
* `location`
* `categories` - Currently the UI only supports one category but we might support more in the future
* `description_short`*
* `ribbon`* 


Short description and ribbon needs to be enabled, please see the events docs. 

## Fully fledged example

```html
<sf-event
    id="{{ component_id_0 }}"
    description="Event"
    image="295x295"
>
    <h1>{{ event.title }}</h1>
    <a href="{{ event.url }}">View event</a>
    
    <div>Ribbon: {{ event.ribbon }}</div>
    <div>{{ event.starts_at | stringToDateFormat:"%e %B %Y" }}</div>
    
    {% if (event.location) %}
    	<div>Location: {{ event.location }}</div>
    {% end_if %}
    
    {% if (event.categories) %}
    	<div>
    	    {% for event.categories as category %}
    	    	{{ category.name }}
    	    {% end_for %}
        </div>
    {% end_if %}
    
    <div style="background: url({{ event.image_escaped }}); width: 250px; height: 250px"></div>
    
    {% if (event.description_short) %}
    	<p>Short description: {{ event.description_short | nl2br }}</p>
    {% end_if %}	
    
    <div><a href="{{ event.ticket_url }}">Buy ticket</a></div>
</sf-event>
```

## A note about the image

If you use `{{ event.image }}` please note that it will look for an image called `primary`. If the system can't find an image with the name primary (i.e. you have named it something else) it will grab the first image uploaded to that event.


## set-landing-page-url-to-current-page

An event might have a custom landing page, instead of the default one based on `event.tpl`. A custom landing page is only used in specific scenarios and can be external or internal. If you have an external event website you can use a url as landing page.

An internal landing page could be useful in this scenario:

Let's say you have a `courses.tpl` and each new course is `course.tpl`. This is just an ordinary blog without connection to Snowfire Events. Inside `course.tpl` you add multiple `<sf-event>` (one for each course date). Now you want to enable the `set-landing-page-url-to-current-page` which will automatically set the landing page for the course to the blog post.