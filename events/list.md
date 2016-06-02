# List of events

## With pagination

### flakeParameters

Each parameter is key:value, multiple parameters are separated with |

* `limit` - Limit the amount of events fetched. Defaults to `50`. You are not allowed to fetch more than that.
* `pagination` - true/false (if you want to paginate the result. Works great with `limit`)
* `type` - `ALL/EVENT/COURSE/INFORMATION (which type of events, defaults to `ALL`)
* `currentPageEvent` - `skip` / `include` (don't include the event you are currently viewing)
* `starts_before`  - `now` (if you want to fetch events that has already started)
* `starts_after`  - `now` (if you want to fetch events that has a future start date)
* `images`- `name(width,height)` (resizes/crops the event image to a new format. Warning: ignores whatever crop the user has made in the admin ui)
* `image` - `width,height` (resizes/crops the first image for the event
* `query` - Search part of event title attribute


```html
{ com_liquid2 (
    id: '1',
    description: 'Events',
    selectablePage: 'false',
    type: 'ALL',
    flake: 'events',
    debug: 'true',
    flakeParameters: 'limit:5|pagination:true|images:primary(100,100)',
    code: '
        <h1>Events</h1>
        
        {% if events %}
            <ul>
                {% for events as event %}
                    <li><a href="{{ event.url }}">{{ event.title }}</a></li>
                {% end_for %}
            </ul>
        {% end_if %}
        
        {% if pagination.last_page > 1 %}
        <nav>
            <ul class="pagination">
                {% if pagination.prev_page_url %}
                    <li>
                        <a href="{{ pagination.prev_page_url }}" aria-label="Previous">
                            <span aria-hidden="true">&laquo;</span>
                        </a>
                    </li>
                {% end_if %}
                {% for pages as page %}
                    {% if pagination.current_page = page %}
                        <li class="active"><a href="{{ page.url }}">{{ page.number }}</a></li>
                    {% else %}
                        <li><a href="{{ page.url }}">{{ page.number }}</a></li>
                    {% end_if %}
                {% end_for %}
                {% if pagination.next_page_url %}
                <li>
                    <a href="{{ pagination.next_page_url }}" aria-label="Next">
                        <span aria-hidden="true">&raquo;</span>
                    </a>
                </li>
                {% end_if %}
            </ul>
        </nav>
        {% end_if %}
    '
) }
```
