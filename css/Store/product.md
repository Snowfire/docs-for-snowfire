Product block
=============

There are two different product blocks in Snowfire. One only exists on the shop layout, and the other one is a content block which can be added everywhere.

Example
-------
Show the product name and price below the image on a white background. 
(this example only changes the design in the shop layout for now)

```css
.shop2 .product .image {
	border: 0;
}

	.column.product .image .overlay,
	.shop2 .product .image .overlay {
		position: static;
		background: #fff;
	}
	
		.shop2 .product .image .overlay:hover {
			background: #fff;
		}
	
		.shop2 .product .image .overlay strong { 
			color: #333;
			text-transform: capitalize;
		}
		
		.shop2 .product .image .overlay a { 
			line-height: 15px;
			margin-bottom: -5px;
		}
```