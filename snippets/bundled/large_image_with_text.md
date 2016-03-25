#Large image with text

### HTML

```html
<div class="wide_image_tall_with_text">
	<div class="content">
        <div class="intro">
            { com_singlerow(
                id: '{{ component_id_1 }}',
                description: 'Headline',
                htmlElement:'span',
                class: 'title'
            ) }

            { com_wysiwyg(
                id: '{{ component_id_2 }}',
                description: 'Subheading'
            ) }

            <span class="sf-button">
                { com_link(
                    id: '{{ component_id_3 }}',
                    description: 'Button'
                ) }
            </span>
        </div>
    </div>

    { com_image2 (
        id: '{{ component_id_0 }}',
        description: 'Image',
        width: '1920',
        height: '900',
        dimensions: 'min',
        resizable: 'false',
        html: '
            <div class="wide_image">
                <div {{ attributes_html | html_decode }} style="background-image:url({{ src }})">
                    <div class="overlay"></div>
                </div>
            </div>
        '
      )
    }
</div>

```


### Javascript
This sets the image height to 70% of window height if the device height is larger than 800px. 

```javascript
$(function(){
    var windowH = $(window).height();
    var wrapperH = $('.wide_image_tall_with_text').height();
    
    if (windowH > wrapperH) {
        $('.wide_image_tall_with_text').css({'height':($(window).height() - 90)+'px'});
    }
    
    if (windowH > 800) {
        $('.wide_image_tall_with_text').css('height', windowH * 0.7);
    }
}
```