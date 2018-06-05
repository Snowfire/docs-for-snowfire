# Support multiple languages

Each language is its own Snowfire account. To make a new language, use the Agency app to clone the account. 
If you don't have access to the Agency app, please get in touch with the support team and they'll help you clone the account.

## Add flags

Add the following JavaScript to the code editor

```js
// Build HTML
var languageBar = $('<div id="change-lang">');

var swedish = $('<a>').attr('href', 'https://www.snowfire.se').attr('title', 'På svenska');
var english = $('<a>').attr('href', 'https://snowfire.net').attr('title', 'In english');

swedish.append($('<img>').attr('src', 'https://d29ly7uq16xz5t.cloudfront.net/images/flags/se_50_v1.png'));
english.append($('<img>').attr('src', 'https://d29ly7uq16xz5t.cloudfront.net/images/flags/gb_50_v1.png'));

languageBar.append(swedish).append(english);

// Style
languageBar.css({
   'position' : 'absolute',
   'top' : '3px',
   'right' : '15px'
});

languageBar.find('img').css({
	'width' : '25px'
});

languageBar.find('a').css({
	'margin-left' : '10px'
});


// All done! Insert it on the page
$('body').append(languageBar);
```
