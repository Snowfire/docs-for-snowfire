# Change menu breakpoint

Add this to `style` css to change the when the website switches between the horizontal menu and the "Menu" button. 
The default value is `992px`

## CSS

```css
.inline-menu {
    @media only screen and (max-width: 1440px) {
        display: none;
    }    
}
.open-menu-btn {
    @media only screen and (max-width: 1440px) {
        display: block;
    }    
}
```
