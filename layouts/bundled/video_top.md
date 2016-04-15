# Video top

Video background with image fallback for moblie. 

### HTML

```html
{{ partial: top.tpl }}

<section class="video-section">
	<div class="video-wrapper">
		<video autoplay muted loop poster="" id="bgvid">
		    <source src="http://d29ly7uq16xz5t.cloudfront.net/sociala-kundraketen3.mp4" type="video/mp4">
		</video>
	</div>
	
	<div class="video-overlay"></div>
	
	{ com_image2 (
	    id: '320',
	    description: 'Image',
	    width: '1920',
	    height: '900',
	    dimensions: 'min-max',
	    resizable: 'false',
	    html: '
	        <div class="video-image">
	            <div {{ attributes_html | html_decode }} style="background-image:url({{ src }})">
	            </div>
	        </div>
	    '
	  )
	}
	
</section>

{{ snippet_area.main }}

{{ partial: footer.tpl }}

```

### CSS

```css
/* ----- Videosection ------ */

.video-section {
    position: relative;
    pointer-events: none;
    margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	.video-section {
        margin-bottom: 30px;
	}
}

.video-wrapper,
.video-image div,
.video-overlay {
	height: 100vh;
}

.video-wrapper {
	min-height: 550px;
    position: relative;
    overflow: hidden;
    z-index: 10;
    width: 100%;
}

video#bgvid { 
    -moz-transition: all 0.5s ease-in-out;
    -o-transition: all 0.5s ease-in-out;
    -webkit-transition: all 0.5s ease-in-out;
    transition: all 0.5s ease-in-out;
    position: absolute;
    bottom: 50%;
    right: 50%;
    -moz-transform: translateX(50%) translateY(50%);
    -webkit-transform: translateX(50%) translateY(50%);
    transform: translateX(50%) translateY(50%);
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    z-index: 45;
    overflow: hidden;
    display: block;
    opacity: 1;
}

@media screen and (max-width: 768px) {
    video#bgvid {
        display: none;
    }
}

/* -- Video moblie image bg -- */

.video-image div {
    position: absolute;
    width: 100%;
    min-height: 500px;
    top: 0;
    background-size: cover;
    background-position: 20%;
    z-index: 0;
    pointer-events: auto;
}

/* -- Video overlay -- */

.video-overlay {
	position: absolute;
    width: 100%;
    top: 0;
    background-color: rgba(29, 36, 42, 0.5);
    min-height: 550px;
    z-index: 10;
    pointer-events: none;
}

/* ----- END: Videosection ------ */


/* ----- Topmenu ------ */

.top-menu-wrapper {
	position: absolute;
	top: 0;
    left: 0;
    width: 100%;
    z-index: 2000;
    background: transparent;
    will-change: transform;
}

/* ----- END: Topmenu ------ */
```