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
* `url`
