Label/Control containers are used in conjuction with a Rounded Control Panel to provide rows of labels and controls as seen in applications such as Calendar and Contacts.

![Label/Control](images/screenshots/labelControlRowBB10.png) 

To use a Label/Control container you first create a &lt;div&gt; with the **data-bb-type="label-control-container"** attribute. You then create a &lt;div&gt; with the **data-bb-type="row"** attribute for each row you want to add to the container.  Then create another &lt;div&gt; for your label with the attribute **data-bb-type="label"** and the contents of this &lt;div&gt; are displayed as the text of the label. The control is then added by adding another bbUI control.  In this example we are using a button and input box.  
```html
<div data-bb-type="screen">
    <div data-bb-type="round-panel"> 
        <div data-bb-type="panel-header">Font Setting</div>
        <div data-bb-type="label-control-container">
            <div data-bb-type="row">
                <div data-bb-type="label">Settings:</div>
                <div data-bb-type="button" onclick="openEditScreen()">Edit</div>
            </div>
            <div data-bb-type="row">
                <div data-bb-type="label">Your Name:</div>
                <input type="text" value="Hello World"/>
            </div>
        </div>
    </div>
</div>
```

## JavaScript Interface

The following JavaScript interfaces are available for dynamically manipulating a Label/Control Container after the screen has been added to the DOM

### show() and hide()

When you want to dynamically show or hide your container you can call it&apos;s **show()** and **hide()** functions.

```javascript
document.getElementById('myContainer').show();
document.getElementById('myContainer').hide();
```

### remove()

As a convenience you can also remove your container from the screen by calling the **remove()** function.

```javascript
document.getElementById('myContainer').remove();
```