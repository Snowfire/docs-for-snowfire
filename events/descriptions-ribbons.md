# Event description & ribbons

## Short description

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

## Ribbon

You can use the ribbon field to add things like "SALE" or "SOLD OUT". Users are free to enter whatever they want in this field, and it is up to you how it looks. Add `<ribbon></ribbon>` in `event.xml` in the `settings` tag exactly as `shortDescription`. 

