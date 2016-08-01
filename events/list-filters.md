# Filter a list of events

It is possible to use the url to dynamically filter the list which is great to use if you only want to display events in a specific location.

## Example

If you have created a page called `Events` using the `events.xml` layout.

`http://your-domain/events?location=Stockholm`

This will display all events which has `Stockholm` as city.

## Parameters

`location` - The city you enter when creating an event. Please note that a non-existing city will display all locations.
`query` - Fuzzy search all events with a specific title. 
`category_id` - A specific category, a numeric value is required
`type` - Works exactly as the [flake parameter type](Snowfire/docs-for-snowfire/blob/master/events/list.md#flakeparameters)
