#Expand div


###HTML

```html
<div class="expand-wrapper">
	<div class="expand-top">
		{ com_wysiwyg ( 
			id:'{{ component_id_0 }}', 
			description:'Enter text here' 
		) }
	</div>
	
	<div class="expand-content">
		{ com_wysiwyg ( 
			id:'{{ component_id_1 }}', 
			description:'Enter text here' 
		) }
	</div>
</div>
```

###CSS

```css 

.expand-wrapper {
	max-width: 830px;
}

.expand-top {
	padding: 20px 50px 20px 30px;
	background: #F0F0EE;
	cursor: pointer;
	position: relative;
}

@media screen and (min-width: 900px){
	.columns.expanddiv + .columns.expanddiv {
		margin-top: 30px;
	}
}

@media screen and (min-width: 600px) and (max-width: 899px){
	.columns.expanddiv + .columns.expanddiv {
		margin-top: -10px;
	}
}

.expand-top:after {
	content:'\f0d7';
	font-family: 'FontAwesome';
	display: block;
    position: absolute;
    top: 28px;
    right: 30px;
    font-size: 24px;
    line-height: 10px;
    -webkit-transform: rotate(-90deg); /* Chrome, Safari, Opera */
    transform: rotate(-90deg);
    
    animation-name: slide-up;
	animation-duration: 0.8s;
	animation-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
	animation-direction: alternate;
	animation-fill-mode: forwards;
}

.expand-top.icon-up:after {
	/*content:'\f0d8';*/
	animation-name: slide-down;
	animation-duration: 0.8s;
	animation-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
	animation-direction: alternate;
	animation-fill-mode: forwards;
}

.expand-content {
	display: none;
	
	padding: 30px;
	background: #f7f7f7;
}

.expand-top p,
.expand-top h1,
.expand-top h2,
.expand-top h3,
.expand-content p{
	margin-bottom: 0;
}

.expand-content.open {
	display: block;
}

@keyframes slide-down {
  from {
    -webkit-transform: rotate(-90deg); /* Chrome, Safari, Opera */
    transform: rotate(-90deg);
  }
  to {
    -webkit-transform: rotate(0deg); /* Chrome, Safari, Opera */
    transform: rotate(0deg);
  }
}

@keyframes slide-up {
  from {
    -webkit-transform: rotate(0deg); /* Chrome, Safari, Opera */
    transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(-90deg); /* Chrome, Safari, Opera */
    transform: rotate(-90deg);
  }
}

```

###Javascript
```Javascript
$('.expand-wrapper').click(function(){
	$(this).find('.expand-content').slideToggle('open');
	$(this).find('.expand-top').toggleClass('icon-up');
});
```