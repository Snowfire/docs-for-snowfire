# Filters

Filters allow you to manipulate output data.

```
[[ tag.name | upper ]]
```

This example uses the `upper` filter which makes all characters in `tag.name` to upper case.

## List of filters


### url

If you want to get the url to a page or tag.

```
[[ id | url(type) ]]
```

Example

```
[[ page.id | url('page') ]]
```

---

### onlyInLiveEdit

If you want to output a variable only when the user is in edit mode. 

Example:

```<p>[[ "Hello World" | onlyInLiveEdit ]]</p>```

Will be rendered as this in edit mode:

```<p>[Hello World]</p>```

And like this for visitors

```<p> </p>```

The [ ] indicates for Snowfire users that this text won't be visible for visitors.

