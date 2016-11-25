# Events

## Usage

Template files for `events` and `event` is built in. To activate events, open `snippet-containers.xml` and add

```
<container>
    <id>events</id>
    <name>Events</name>
</container>  
```

This will allow you to create a new page and choose `Events` in the page type dropdown. 
After you've created your events page you are able to create individual events using the default template.

A simple way to customise it is to only use CSS and override the default styles.

### Advanced – Create your own event templates

First, you will need to create a new template with a custom name, i.e. `my-events`. Then you need to edit `my-events.xml` to tell Snowfire it is a events page. 
You will also need a `my-event` template for the individual event. Take a look at the xml files below to see what you to add.

* [Layout XML files example](xml-files.md)
* [List of events](events-list.md) - `events` template
* [Event page](event.md) - `event` template
* [Categories](categories-list.md)
* [Images](images.md)
* [Descriptions & Ribbons](descriptions-ribbons.md)
* [Buy ticket](buy-ticket.md)
