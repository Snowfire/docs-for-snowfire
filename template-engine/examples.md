# Examples 

## Tags

A list of tags which filters the current page to only show a keys component with data from the active tag

```html
<ul>
    [% set current = current() %]
    [% for tag in childrenTags('limit: 10') %]
        <li>
        <a href="/[[ current.page.id | url('page') ]]/tags:[[ tag.name ]]">[[ tag.name ]]</a>
        </li>
    [% endfor %]
</ul>
```
