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


