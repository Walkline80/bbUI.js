The bbUI framework uses HTML5 **data-** attributes to allow for markup-based initialization and configuration of controls.  To avoid naming conflicts with other plugins or frameworks that also use data- attributes the bbUI controls use a **data-bb-** prefix.

## [Action Bar](Action-Bar)

Divs with **data-bb-type="action-bar"** are styled to look like BlackBerry 10 action bars

<table>
<tr>
<td><b>data-bb-back-caption</b></td>
<td>Caption to be displayed for the action bar back button</i></td>
</tr>
</table>

## [Action Bar (Action)](Action-Bar)

Action divs must be nested inside an action bar and use the **data-bb-type="action"** attribute 

<table>
<tr>
<td><b>data-bb-tab-style</b></td>
<td>action | tab</b></td>
</tr>
<tr>
<td><b>data-bb-img</b></td>
<td>Path to image to be used in the action item</td>
</tr>
<tr>
<td><b>data-bb-overflow</b></td>
<td><b>false</b> | true</td>
</tr>
<tr>
<td><b>data-bb-signature</b></td>
<td><b>false</b> | true</td>
</tr>
<tr>
<td><b>data-bb-visible</b></td>
<td><b>true</b> | false</td>
</tr>
<tr>
<td><b>data-bb-pin</b></td>
<td><b>false</b> | true &nbsp;&nbsp;<i>NOTE: true is only supported for button actions</i></td>
</tr>
<tr>
<td><b>data-bb-accent-text</b></td>
<td>Secondary text to show on an action<i>NOTE: this is only supported on tab actions for display in the tab overflow</i></td>
</tr>
</table>

The text used as the innerHTML of the action &lt;div&gt; will be used as the caption for the tab/button.

## [Activity Indicator](Activity-Indicator)

To create an activity indicator use the **data-bb-type="activity-indicator"** attribute. 

<table>
<tr>
<td><b>data-bb-size</b></td>
<td>small | <b>medium</b> | large </td>
</tr>
</table>

## [BBM Bubble](BBM-Bubbles)

Divs with **data-bb-typ="bbm-bubble"** will be styled to look like a bubble in the BBM app.  A BBM bubble can contain one or more items.

<table>
<tr>
<td><b>data-bb-style</b></td>
<td>right | left</td>
</tr>
</table>

## [BBM Bubble (Item)](BBM-Bubbles)

A BBM bubble conversation item must be contained in a BBM bubble and has the **data-bb-type="item"** attribute.

<table>
<tr>
<td><b>data-bb-img</b></td>
<td>Path to image to be used for the item</td>
</tr>
</table>

The innerHTML of the item &lt;div&gt; is used as the text to show in the conversation item.

## [Button](Buttons)

Divs with **data-bb-type="button"** are styled to be BlackBerry looking buttons

<table>
<tr>
<td><b>data-bb-disabled</b></td>
<td><b>false</b> | true</td>
</tr>
<tr>
<td><b>data-bb-img</b></td>
<td>Path to image to be used for the button</td>
</tr>
</table>


## [Context Menu](Context-Menus)

Divs with the **data-bb-type="context-menu"** will be styled as a BlackBerry 10 press-and-hold context menu.  A context 
menu contains one or more actions

## [Context Menu (Action)](Context-Menus)

Context menu actions are contained in a context menu &lt;div&gt; and have the **data-bb-type="action"** attribute

<table>
<tr>
<td><b>data-bb-img</b></td>
<td>Path to image to be used for the action</td>
</tr>
<tr>
<td><b>data-bb-pin</b></td>
<td><b>false</b> | true</td>
</tr>
</table>

The innerHTML of the action &lt;div&gt; is used as the text to show in the menu item.

## [DropDown](DropDowns)

Dropdowns are created by simply adding a &lt;select&gt; element to the screen

<table>
<tr>
<td><b>data-bb-label</b></td>
<td>Optional label text for a BlackBerry 10 Dropdown</td>
</tr>
<tr>
<td><b>data-bb-style</b></td>
<td>stretch</td>
</tr>
</table>

For BlackBerry 10 you can also add a second line of text to the &lt;option&gt; being displayed when the dropdown is opened.

<table>
<tr>
<td><b>data-bb-accent-text</b></td>
<td>Optional label text to appear on the second line of the option in the dropdown when open</td>
</tr>
</table>

## [Control Group](Control-Groups)

Divs with the **data-bb-type="round-panel"** are styled as a control group

## [Control Group (Header)](Control-Groups)

Control group headers are contained in a control group and have the **data-bb-type="panel-header"** attribute

## File Input

Inputs of type="file" are styled in BlackBerry 10 to appear as a standard BlackBerry 10 button.  You can customize the caption of the file input button using the following attribute

<table>
<tr>
<td><b>data-bb-caption</b></td>
<td>Caption of File button</td>
</tr>
</table>


## [Grid List](Grid-List)

Divs with **data-bb-type="grid-layout"** are styled to be a BlackBerry 10 image grid

<table>
<tr>
<td><b>data-bb-style</b></td>
<td><b>landscape</b> | square</td>
</tr>
<tr>
<td><b>data-bb-context</b></td>
<td><b>false</b> | true</td>
</tr>
<tr>
<td><b>data-bb-header-justify</b></td>
<td><b>center</b> | left | right</td>
</tr>
<tr>
<td><b>data-bb-header-style</b></td>
<td><b>default</b> | solid</td>
</tr>
</table>

## [Grid List (Group)](Grid-List)

A grid list group must be contained in a grid list control and has the **data-bb-type="group"** attribute.  A group can contain one or more rows.

<table>
<tr>
<td><b>data-bb-title</b></td>
<td>Optional text to use as a caption in the group heading</td>
</tr>
</table>

## [Grid List (Row)](Grid-List)

A grid list row must be contained in a grid list group and has the **data-bb-type="row"** attribute.  A row contains one or more items

<table>
<tr>
<td><b>data-bb-columns</b></td>
<td>Optional numeric attribute specifying the number of desired columns for the row</td>
</tr>
</table>



## [Grid List (Item)](Grid-List)

A grid list item must be contained in a grid list row and has the **data-bb-type="item"** attribute.

<table>
<tr>
<td><b>data-bb-img</b></td>
<td>Path of image to display</td>
</tr>
<tr>
<td><b>data-bb-title</b></td>
<td>Title text to display on image</td>
</tr>
</table>

Sub-title text for the image is contained as the innerHTML of the &lt;div&gt;

## [Image List](Image-List)

Divs that use the **data-bb-type="image-list"** attribute will be styled as a BlackBerry image list

<table>
<tr>
<td><b>data-bb-context</b></td>
<td><b>false</b> | true</td>
</tr>
<tr>
<td><b>data-bb-images</b></td>
<td><b>display</b> | none</td>
</tr>
<tr>
<td><b>data-bb-image-placeholder</b></td>
<td>Path of image to display</td>
</tr>
<tr>
<td><b>data-bb-image-effect</b></td>
<td><b>none</b> | fade </td>
</tr>
<tr>
<td><b>data-bb-header-justify</b></td>
<td><b>center</b> | left | right</td>
</tr>
<tr>
<td><b>data-bb-header-style</b></td>
<td><b>default</b> | solid  &nbsp;&nbsp;<i>NOTE: solid is only supported for BlackBerry 10 and PlayBook. </i></td>
</tr>
<tr>
<td><b>data-bb-style</b></td>
<td><b>default</b> | arrowlist | arrowbuttons | addbuttons | removebuttons  &nbsp;&nbsp;<i>NOTE: BB5/6/7 only supports default and arrowlist.</i></td>
</tr>
</table>

## [Image List (Header)](Image-List)

A header divider &lt;div&gt; is with the **data-bb-type="header"** is used to separate items in an image list. The contents of the header innerHTML is used as the display caption.

## [Image List (Item)](Image-List)

An Image List item is a &lt;div&gt; that represents a line item in a list using the attribute **data-bb-type="item"**.  This item is nested in an Image List.

<table>
<tr>
<td><b>data-bb-img</b></td>
<td>Path of image to display</td>
</tr>
<tr>
<td><b>data-bb-title</b></td>
<td>Title text to display on image</td>
</tr>
<tr>
<td><b>data-bb-accent-text</b></td>
<td>Accent text to show with the item</td>
</tr>
</table>

## [Label/Control Container](Label-Control-Container)

Divs with the attribute **data-bb-type="label-control-container"** are styled as a control container for BlackBerry

## [Label/Control Container (Row)](Label-Control-Container)

Rows are created in the Label Control container by using divs with the **data-bb-type="row"** attribute.

## [Label/Control Container (Label)](Label-Control-Container)

Labels are used for a row by specifying a div with the **data-bb-type="label"** attribute.

## [Menu](Menus)

Divs that use the **data-bb-type="menu"** attribute will be styled as a menu.  Menus contain one or more menu items or separators

## [Menu (Item)](Menus)

Menu items contained in a Menu use the **data-bb-type="menu-item"** attribute

<table>
<tr>
<td><b>data-bb-img</b></td>
<td>Path to image to be used for the item</td>
</tr>
<tr>
<td><b>data-bb-selected</b></td>
<td><b>false</b> | true</td>
</tr>
</table>

## [Menu (Separator)](Menus)

Menu separators contained in a Menu use the **data-bb-type="menu-separator"** attribute

## [Pill Buttons](Pill-Buttons)

Divs that use the **data-bb-type="pill-buttons"** will be styled as a BlackBerry pill button group. This group can contain
one or more buttons.

## [Pill Buttons (Button)](Pill-Buttons)

Buttons in a pill button group have the **data-bb-type="pill-button"** attribute

<table>
<tr>
<td><b>data-bb-selected</b></td>
<td><b>false</b> | true</td>
</tr>
</table>

The innerHTML of the button &lt;div&gt; contains the caption of the button.

## [Screen](Screens)

Divs with **data-bb-type="screen"** are styled to be a BlackBerry screen

<table>
<tr>
<td><b>data-bb-effect</b></td>
<td><b>none</b> | fade | slide-left | slide-right | slide-up | slide-down</td>
</tr>
</table>


## [Scroll Panel](Scroll Panel)

Divs with **data-bb-type="scroll-panel"** are styled to scroll its contents

## [Title Bar](Screens)

Title bar divs must be nested inside a screen div and use the **data-bb-type="title"** attribute.

<table>
<tr>
<td><b>data-bb-caption</b></td>
<td>Caption to show in the title area</td>
</tr>
<tr>
<td><b>data-bb-back-caption</b></td>
<td>Caption to show in the &quot;back&quot; button on PlayBook and BB10</td>
</tr>
<tr>
<td><b>data-bb-action-caption</b></td>
<td>Caption to show in the second right hand button on BB10 styling</td>
</tr>
<tr>
<td><b>data-bb-img</b></td>
<td>Image to show in the top right hand corner of the title with BB10 styling</td>
</tr>
<tr>
<td><b>data-bb-accent-text</b></td>
<td>Second line of text to show under the title caption when using BB10 styling</td>
</tr>
</table>

 

## [Toggle Buttons](Toggle-Buttons)

Toggle buttons are defined with the **data-bb-type="toggle"** attribute.

<table>
<tr>
<td><b>data-bb-checked</b></td>
<td><b>false</b> | true</td>
</tr>
<tr>
<td><b>data-bb-on</b></td>
<td>Caption to show in the toggle &quot;on&quot; position</td>
</tr>
<tr>
<td><b>data-bb-off</b></td>
<td>Caption to show in the toggle &quot;off&quot; position</td>
</tr>
<tr>
<td><b>data-bb-disabled</b></td>
<td><b>false</b> | true</td>
</tr>
</table>