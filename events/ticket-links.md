# Link to the buy ticket page

The default link. Please note that `{{ currentQueryString }}` allows us to forward an optional discount in the link.

```html
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&{{ currentQueryString }}">
  Buy ticket
</a>
```

--

Tell the system that we are a person (i.e. not a company)

```html
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&part=person&{{ currentQueryString }}">
  Buy ticket
</a>
```

--

Tell the system that we are a company and ask for company name and VAT ID/TAX ID

```html
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&part=company&company=1&{{ currentQueryString }}">
  Buy ticket
</a>
```

--

Don't run any triggers after a successful payment (a trigger is a user defined action that happens after a successful payment)

```html
<a href="{{ flake.public_url }}/events/ticket?pid={{ page.id }}&part=person&trigger=0&{{ currentQueryString }}">
  Buy ticket
</a>
```
