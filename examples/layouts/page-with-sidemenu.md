# Page with sidemenu

#### `page_with_sidemenu.tpl`

```html
{{ partial: top.tpl }}

<div class="container">
    <div class="row">
        <div class="col-md-9">
            {{ snippet_area.main }}
        </div>
        <div class="col-md-3">

            <!-- Sidemenu -->
            <div class="sf-sidemenu-wrapper">
                <div class="sf-sidemenu">
                    { com_menu (
                        id:'3',
                        description:'Sub navigation',
                        class: 'sf-sidemenu-inner',
                        childrenLevels:'2',
                        hasChildrenClass:'has-children',
                        childHasChildrenClass:'child-has-children',
                        itemHtml:'<li %class%><a href="%link%" class="bara">%name%</a></li>',
                        childItemHtml:'<li %class% class="second-child"><a href="%link%">%name%</a></li>',
                        useRootParentMenuItemChildren: 'true'
                    ) }
                </div>
            </div>
            <!-- END: Sidemenu -->

        </div>
    </div>
</div>


{{ partial: footer.tpl }}
```

#### `page_with_sidemenu.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    <options>
        <component_id_offset>1000</component_id_offset>
    </options>

    <snippets area="main" width="1130" column_spacing="5%" all_user_snippets="true">
        <snippet id="text" />
        <snippet id="video" />
        <snippet id="form" />
        <snippet id="map" />
        <snippet id="slider" />
        <snippet id="latest_posts" />
        <snippet id="quote2" />
        <snippet id="facebook" />
        <snippet id="facebook_comments" />
        <snippet id="sociallinks" />
        <snippet id="product" />
        <snippet id="sf_btn" />

        <snippet id="wide_image" />
        <snippet id="wide_image_with_text2" />
        <snippet id="statement" />
        <snippet id="top_heading" />
        <snippet id="wide_image_tall_with_text"/>
        <snippet id="product-collection"/>
        <snippet id="popup-image-gallery"/>
        <snippet id="go-back"/>
        <snippet id="html" />
        <snippet id="color_block" />
    </snippets>

    <snippets area="footer" width="1160" column_spacing="5%" sync="true" add_button="Add to footer">
        <snippet id="text_synced" />
        <snippet id="video_synced" />
        <snippet id="form_synced" />
        <snippet id="map_synced" />
        <snippet id="slider_synced" />
        <snippet id="latest_posts_synced" />
        <snippet id="quote2_synced" />
        <snippet id="facebook_synced" />
        <snippet id="facebook_comments" />
        <snippet id="sociallinks_synced" />
        <snippet id="product_synced" />
        <snippet id="sf_btn_synced" />
        <snippet id="wide_image_synced" />
        <snippet id="html_synced" />
    </snippets>

</snippet_container>
```