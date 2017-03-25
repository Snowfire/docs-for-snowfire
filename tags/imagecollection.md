# Image collection

Great to use for sliders or image galleries. 


## Parameters

* `html-element`
* `width`
* `height`
* `placeholder-height`
* `aspect-ratio` (float) - Lock aspect ratio.
* `link-to-image` (boolean) - Automatically link to the source image file.

### Inside the tag

Variables:

* `%image%` – HTML code for image with link if set.

### aspect-ratio

With aspect ratio set, image size is calculated by `width × width / aspect ratio`.  
An aspect ratio of `2` is equal to 2:1 proportion.


## Slider example using Flexslider

```html
<div class="flexslider">
    <sf-imagecollection
        id="{{ component_id_0 }}"
        description="Add image"
        html-element="ul"
        class="slides"
        width="{{ column_width }}"
        autodetect-width="true"
        height="400"
        crop="true"
    >
        <li>%image%</li> 
    </sf-imagecollection>
</div>
```
