Event
=====

```xml
{ com_event (
  id: '1', 
  description: 'Event',
  image: '295x295',
  html: '
    
    <h1>{{ event.title }}</h1>
    <div><img src="{{ event.image }}" /></div>
    <a href="{{ event.url }}">View event</a>
    
  '
)}
```

Parameters
----------

* `image` -  **required**, the width/height of the primary image

Event properties
---------------

These are available as `{{ event.X }}` in the `html` parameter. Example: `{{ events.title }}`

* `title`
* `image` - The event image in the resolution you have decided in the `image` parameter
* `image_escaped` - The event with escaped characters, use this when you have the image as a css background image
* `url`
* `description`
* `starts_at` - Use `{{ event.starts_at | stringToDateFormat:"%e %B %Y" }}` to choose date format
* `location`
* `categories` - Currently the UI only supports one category but we might support more in the future
* `description_short`*
* `ribbon`* 


Enable short description & ribbon
---------------------------------

If you need a specific field for a shorter description and/or a ribbon text you can enable it in `event.xml` by adding the following:

```xml
<template_config>
    <settings>
        [..]
        <shortDescription length="140"></shortDescription>
        <ribbon></ribbon>
    </settings>
</template_config>
```

A ribbon is a single line of text with max 255 characters. 


Fully fledged example
---------------------

```xml
{ com_event (
  id: '1', 
  description: 'Event',
  image: '295x295',
  html: '
    
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
    
  '
)}
```
