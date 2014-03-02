Product block
=============

There are two different product blocks in Snowfire. One only exists on the shop layout, and the other one is a content block which can be added everywhere.

Example
-------
Show the product name and price below the image on a white background. This changes the CSS on two places, in the shop layout and the product content block.

```css
.column.product .image,
.shop2 .product .image {
	border: 0;
}

	.column.product .image .overlay,
	.shop2 .product .image .overlay {
		position: static;
		background: #fff;
	}

		.column.product .image .overlay:hover,
		.shop2 .product .image .overlay:hover {
			background: #fff;
		}

		.column.product a,
		.shop2 .product a {
			padding: 0 !important;
		}

		.column.product .image .overlay strong,
		.shop2 .product .image .overlay strong {
			color: #333;
			text-transform: capitalize;
		}

		.column.product .image .overlay a,
		.shop2 .product .image .overlay a {
			line-height: 15px;
			margin-bottom: -5px;
		}
```
