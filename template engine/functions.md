# Functions

Functions allow you to get data from the database. Example:

```
[% for tag in tags('limit: 5') %]
    <div>
    	[[ tag.name ]]
    </div>
[% endfor %]
```

This example uses a function called `tags` and sends `limit` and `pageLimit` as parameters. This function returns an array which makes it possible to use in a `for` loop.

## List of functions

### tags

Parameters:
* limit &ndash; (numeric, required)
* pageLimit &ndash; (numeric, optional)

Returns an array of tags:

```
[
	{
		"name": "Apple",
		"id": 41,
		"pages": [
			{
				"name": "Fruits",
				"id": 78 		
			}
		]
	}
]
```

Example access:

```
[% set tags = tags('limit: 5', 'pageLimit: 3') %]

<!-- Display the first tag name -->
[[ tags[0].name ]]
```