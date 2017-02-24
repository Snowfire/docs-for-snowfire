# Membership

Membership allows a visitor to register and sign in on a website. Signed in users may access protected pages. 
It is up to you if you want to allow anyone to register, or if it is only administrators who can invite members.

## Examples

### Register link

```
{ com_liquid2 (
    id: '{{ component_id }}',
    description: 'Join us',
    selectablePage: 'false',
    debug: 'false',
    code: '
        <a href="{{ flake.public_url }}/members/signup?pid={{ page.id }}">Join us</a>
    '
)}
```

### Sign in / out

```
{ com_liquid2 (
	id: '{{ component_id }}',
	description: 'Membership',
	selectablePage: 'false',
	flake: 'members/session',
	debug: 'false',
	code: '
		{% if loggedIn %}
			<a href="{{ flake.public_url }}/members/logout?pid={{ page.id }}">Sign out</a>
		{% else %}
			<a href="{{ flake.public_url }}/members/login?pid={{ page.id }}">Sign in</a>
		{% end_if %}
  '
)}
```

### Show signed in information

```
{ com_liquid2 (
	id: '{{ component_id }}',
	description: 'Membership',
	selectablePage: 'false',
	flake: 'members/person',
	debug: 'false',
	code: '
		{% if loggedIn %}
			Logged in as {{ first_name }} {{ last_name }}   |   
  			<a href="{{ flake.public_url }}/members/logout?pid={{ page.id }}">Sign out</a>
		{% else %}
		    You are not signed in
		{% end_if %}

	'
)}
```
