#Partial: top


### HTML

```html
<script>
/* ---- Dropdown ------ */
$(function(){

	var t;
	var timers = [];

	function setDropdownListeners() {

		$('.has_dropdown').mouseover(
			function(){

				timerStop();

				// Clear siblings
				$(this).siblings().removeClass('hover');
				$(this).siblings().find('ul li').each(function(){
					$(this).removeClass('hover');
				})
				
				$(this).addClass("hover");

			}
		);

		$('.inline-menu ul').mouseleave(function(){
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

/* ---- END: Dropdown ------ */

</script>

<div class="top-menu-wrapper">
    <header class="container top-menu component-dropdown">
        <div class="row">
            <div class="col-sm-12">
                <div class="tbl">
                    <div id="logo-wrapper">
                        <div id="logo">
                            { fnc_designstudio ( part:'header' ) }
                        </div>
                    </div>
                </div>

                <nav class="inline-menu">
                    { com_menu (
                    id: '1',
                    description: 'Menu',
                    syncId: '1',
                    childrenLevels: '1',
                    hasChildrenClass: 'has_dropdown',
                    itemHtml: '<li %class%><a href="%link%">%name%</a></li>',
                    childItemHtml: '<li %class%><a href="%link%">%name%</a></li>'
                    ) }
                </nav>

                <div class="open-menu-btn sf-bar-menu-button-right">
                    <a>Menu</a>
                </div>

                <nav id="drawer-right" class="sf-drawer sf-drawer-right sf-drawer-closed drawer-navigation nav-right">
                    <div class="inside">

                        <a class="close-nav"></a>

                        <div class="clearfix"></div>

                        { com_menu (
                            id: '2',
                            description: 'Menu',
                            syncId: '1',
                            childItemHtml: '<li %class%><a href="%link%">%name%</a></li>',
                            childrenLevels: '1',
                            hasChildrenClass: 'has_dropdown',
                            itemHtml: '
                            <li %class%>
                                <a href="%link%">
                                    %name%
                                </a>
                            </li>
                            '
                        ) }

                    </div>
                </nav>

            </div>
        </div>
    </header>
</div>

```
