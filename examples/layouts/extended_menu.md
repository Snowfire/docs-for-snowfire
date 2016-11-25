# Partial: extended menu

### top.tpl

```html
<!-- Extended top -->

<div class="top-menu-wrapper">
    <header class="container top-menu component-extended">

        <nav id="extended-right" class="sf-extended sf-extended-right sf-extended-closed extended-navigation extended-right">
            <div class="inside">

                <a class="close-nav"></a>

                <div class="clearfix"></div>

                { com_menu (
                    id: '6',
                    syncId: '6',
                    description: 'Menu',
                    childItemHtml: '<li %class%><a href="%link%">%name%</a></li>',
                    childrenLevels: '1',
                    hasChildrenClass: 'has_dropdown',
                    itemHtml: '
                    <li %class%>
                        <a href="%link%" class="dropdown-toggle">
                            %name%
                        </a>
                    </li>
                    '
                ) }

            </div>
        </nav>

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
                        syncId: '3',
                        description: 'Menu',
                        childrenLevels: '0',
                        lastClass: 'sf-extended-button-right',
                        itemHtml: '<li %class%><a href="%link%">%name%</a></li>'
                    ) }
                </nav>

                <div class="open-menu-btn sf-bar-menu-button-right">
                    <a>Menu</a>
                </div>


                <!-- This is the mobile navigation -->

                <nav id="drawer-right" class="sf-drawer sf-drawer-right sf-drawer-closed drawer-navigation nav-right">
                    <div class="inside">

                        <a class="close-nav"></a>

                        <div class="clearfix"></div>

                        { com_menu (
                            id: '11',
                            syncId: '4',
                            description: 'Menu',
                            lastClass: 'sf-extended-button-right',
                            childrenLevels: '0',
                            itemHtml: '
                                <li %class%>
                                    <a href="%link%" class="first-child">
                                        %name%
                                    </a>
                                </li>
                            '
                        ) }

                        { com_menu (
                            id: '10',
                            syncId: '7',
                            description: 'Menu',
                            childItemHtml: '<li %class%><a href="%link%">%name%</a></li>',
                    		childrenLevels: '1',
                    		hasChildrenClass: 'has_dropdown',
                            itemHtml: '
                                <li %class%>
                                    <a href="%link%" class="first-child">
                                        %name%
                                    </a>
                                </li>
                            '
                        ) }

                    </div>
                </nav>

                <!-- End: mobile navigation -->


            </div>
        </div>
    </header>
</div>

<!-- END: Extended top -->

```

###CSS

```CSS
.extended-navigation ul .has_dropdown {
    list-style-type: none;
    margin-bottom: 20px;
}

.extended-navigation .has_dropdown ul li > a,
.extended-navigation .has_dropdown ul li ~ li a {
	text-transform: none;
	font-weight: 400;
	padding: 5px 0;
}

.component-extended .extended-navigation ul .has_dropdown > a {
	padding-bottom: 0;
}

```