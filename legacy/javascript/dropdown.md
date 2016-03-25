## Make sure dropdown does not close immediately on mouse leave

```javascript
/* Dropdown */
$(function(){

	var t;
	var timers = [];

	function setDropdownListeners() {

		$('.has-children').mouseover(
			function(){

				timerStop();

				// Clear siblings
				$(this).siblings().removeClass('hover');
				$(this).siblings().find('ul.sub-menu li').each(function(){
					$(this).removeClass('hover');
				})

				$(this).addClass("hover");

			}
		);

		$('header nav ul').mouseleave(function(){
			timerStart();
		});

		function timerStop(){
			for(var i=0; i<timers.length; i++){
				clearTimeout(timers[i]);
			}
		}

		function timerStart(){
			var t = setTimeout(clearHoverStates, 500);
			timers.push(t);
		}

		function clearHoverStates(){
			$('li').each(function(){
				$(this).removeClass('hover');
			});
		}

	}

	setDropdownListeners();



});
```
