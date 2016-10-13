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

### current()

Retrieves information about the current page and request. Example:

```
[% set current = current() %]			
<h1>[[ current.tag.name ]]</h1>
```

This is the data `current()` returns:

```json
{
	"page": {
		"id": "41",
		"name": "About us",
		"url": "/about-us"
	},
	"tag": {
		"id": "314",
		"name": "Weather"
	}
}
```



### childrenTags()

Will get the current pages sub pages tags. I.e. if you are on the main blog layout and want to get all tags from posts.

Parameters:
* limit &ndash; (numeric, required)
* pageLimit &ndash; (numeric, optional)

Returns an array of tags:

```json
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

---

### siblingTags()

If you are on the single blog post layout and want to get all tags on the blog. This function works exactly like `childrenTags()` with the same parameters, same return etc.

---

### link()

Used to create dynamic links to system functions.

`[[ link('section:action') ]]`

Parameters:
* member &ndash; (login or logout)

Example

`[[ link('member:login') ]]`
