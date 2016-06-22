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
* `setLandingPageUrlToCurrentPage` - optional, please read below about this option

Event properties
---------------

These are available as `{{ event.X }}` in the `html` parameter. Example: `{{ events.title }}`

* `title`
* `image` - The event image in the resolution you have decided in the `image` parameter
* `image_escaped` - The event with escaped characters, use this when you have the image as a css background image
* `ticket_url`
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
    
    <div><a href="{{ event.ticket_url }}">Buy ticket</a></div>
    
  '
)}
```

setLandingPageUrlToCurrentPage
------------------------------

An event might have a custom landing page, instead of the default one based on event.tpl. A custom landing page is only used in specific scenarios and can be external or internal. If you have an external event website you can use a url as landing page.

An internal landing page could be useful in this scenario:

Let's say you have a `courses.tpl` and each new course is `course.tpl`. This is just an ordinary blog without connection to Snowfire Events. Inside `course.tpl` you add multiple `com_event` (on for each course date). Now you want to enable the `setLandingPageUrlToCurrentPage` which will automatically set the landing page for the course to the blog post.
