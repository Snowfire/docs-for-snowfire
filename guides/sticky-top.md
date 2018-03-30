Identify your header selector. On inspire it is `.top-menu-wrapper` and add the following:

```css
.top-menu-wrapper {
    position: fixed;
    width: 100%;
    z-index: 9999;
    top: 0;
}
```

Add a margin to the body element since the header is no longer a part of the DOM flow.

```css
body {
    margin-top: 60px;
}
```

That's it!

If you want to customize more of the behaviour, this javascript is helpful:

```js
$(document).ready(function() {
    
  // Wait 90px of scroll height before doing anything
  $(window).scroll(function (event) {
    if ($(window).scrollTop() > 90) {
      $('body').addClass('is-scrolling');
    } else {
      $('body').removeClass('is-scrolling');
    }
  });

});
```

This will add the `.is-scrolling` class to the `<body>` during scroll. 
This makes it possible to resize the logo, resize the header etc. For example:

```css
.is-scrolling .top-menu-wrapper {
  background: red;
}
```
