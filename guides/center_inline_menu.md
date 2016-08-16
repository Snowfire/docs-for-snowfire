# Center inline menu

Add this to `global.css` to center the inline menu. You might need to adjust the `.component-dropdown` height and the `.inline-menu` margin-top, depending on the height of your logo. 

###CSS

```css
.component-dropdown {
	height: 140px;
}

.inline-menu {
    float: none;
    text-align: center;
    margin-top: 90px;
}

.inline-menu ul {
	float: none;
}
```