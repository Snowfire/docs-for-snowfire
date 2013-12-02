Twitter
=====

```html
{ com_twitter(
    id:'1',
    description:'Twitter',
    htmlElement:'div',
    width: '500',
    itemHtml:'
            <div class="status">
                <p>%status%</p>
                %photos%
                <div class="actions">	
                	<div class="interaction">
                		<a href="https://twitter.com/intent/tweet?in_reply_to=%id%" target="_blank">Reply</a> · 
                		<a href="https://twitter.com/intent/retweet?tweet_id=%id%" target="_blank">Retweet</a>  · 
						<a href="https://twitter.com/intent/favorite?tweet_id=%id%" target="_blank">Favorite</a>
                	</div>
	                <div class="author">
		                <a href="%link%" target="_blank">
		                	<span class="name">%name% &ndash;</span>
			                <span class="date">
			                	%date_relative%
			                </span>
						</a>
	                </div>
				</div>
	        </div>'
) }
```

Parameters
----------

* width
* htmlElement
* itemHtml - Controls the output, see below

### `itemHtml`

Uses % for variables. Available variables:

* %status% - the tweet
* %photos% - outputs img tags if the tweet contains photos
* %id% - the twitter id of the specific tweet
* %link% - link to the tweet on twitter.com
* %date_relative% - a relative date for when the tweet was posted