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
* only &ndash; (comma separated, optional) &ndash; `only: Sun, Cloud` (will only return these two tags if they exist)
* exclude &ndash; (comma separated, optional) &ndash; `exclude: Sun, Cloud` (will return all tags except Sun and Cloud)
* pageId &ndash; (numeric, optional) &ndash; Specify the parent page to fetch children tags from. If not provided, we'll use the current page id

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

---

### getFormUrl()

Used to get "action" name for the form that uses a remote api and storing that response data in the cache

Parameters:
* url &ndash; (string, required)
* redirect_to &ndash; (string, required)

where url is the api you want to send/get data from and redirect_to is what page you want to redirect to after

Example access:
```
<form method="post" action="[[getFormUrl('url: http://remoteapiurl', 'redirect_to: nexturl')]]">
```

---

### getDataFromCache()

Used to get data from cache that we previously stored  

Returns an array of data depending on the remote api:

Example:

```
{  
  "cars":[  
    {  
      "car":[  
        {  
          "id":"25",
          "klass":"person",
          "korkort":"B"
        }
      ]
    },
    {  
      "rent":{  
        "Id":"3",
        "Grupp":"B"
      }
    }
  ]
}
```

Example access:
```
[% set data = getDataFromCache() %]

<!-- Display the id of the car from example -->
[[ data.cars.car.id ]]

<!-- Display the group of the rent from example -->
[[ data.cars.rent.Grupp ]]
```

---




