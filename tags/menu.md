# Menu

Add a menu navigation element to your page. Usually used in a top or bottom partial. 

## Simple example

```javascript
<sf-menu
    id="1"
    description="Menu"
>
    <li><a href="%link%" %class% id="menu-%nameSanitized%">%name%</a></li>
</sf-menu>
```

## Advanced example

```
{ com_menu ( 
    id: '1',
    description: 'Menu',
    itemHtml: '<li><a href="%link%" %class% id="menu-%nameSanitized%">%name%</a></li>'
) }
```

## Parameters

Please note that you will need to use the advanced syntax example of you plan to ute `childItemHtml`. If you are using the simple syntax, please convert the camelCase parameters to kebab case (i.e `hasChildrenClass` becomes `has-children-class`

* `menuId` - The ID of the menu. The component is not changeable from Live edit if this is specified.
* `parentId` - Parent menu ID. Defaults to 0.
* `activeClass` - HTML class of active elements. Defaults to active. %classValue% or %class% must be set.
* `firstClass` - HTML class of first element. Defaults to nothing. %classValue% or %class% must be set.
* `lastClass` - HTML class of last element. Defaults to nothing. %classValue% or %class% must be set.
* `hasChildrenClass` - HTML class whether the item has children. Defaults to nothing. %classValue% or %class% must be set.
* `htmlElement` - Specifies what html element should be used. Defaults to ul.
* `reverse` - If the item order should be reversed. Defaults to false.
* `between` - Html to insert between every item.
* `childrenLevels` - How many levels (generations?) of children to display. Defaults to 0. Note: This must be set to something greater than 0 for child items to be displayed.
* `child*` - To change options on children, prepend child to any option except menuId, parentId, childrenLevels, useRootParentPageChildren, noCreateButton and activeByPageStructure. For example, to set itemHtml, use childItemHtml.
* `useRootParentPageChildren` - This will automatically create a menu from the root parent's children pages. Defaults to false.
* `noCreateButton` - boolean. Set if no "Create new..." link in the menu is wanted.
* `activeByPageStructure` - boolean. Instead of using menu structure to detect what item is active, use page structure.
* `itemHtml` - HTML markup for an item. Defaults to `<li><a %class% href="%link%">%name%</a></li>` (Use %description% to get output from the optional description field when editing a menu item)
