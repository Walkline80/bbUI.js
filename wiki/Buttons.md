![Buttons](images/screenshots/labelControlRowBB10.png)

Buttons can be used pretty much anywhere.  Creating a button starts by creating a &lt;div&gt; with the **data-bb-type="button"** attribute. By default a button will size itself to the text used for the caption.  You can however use the **data-bb-style="stretch"** setting for a button to make it stretch to the total width of the container where it is embedded. 

### onclick

To add a click handler to the button simply add an "onclick" event to the &lt;div&gt;.

```html
<div data-bb-type="screen">
    <div data-bb-type="panel-header">Font</div>
        <div data-bb-type="label-control-horizontal-row">
            <div data-bb-type="label">Font Style:</div>
            <div data-bb-type="button" onclick="alert('click');" id="plain">Plain</div>
        </div>
    </div>
</div>
```

### Images

BlackBerry 10 and PlayBook styled buttons support the ability to add an image by setting the **data-bb-img** attribute to the path to your image.  
```html
    <div data-bb-type="button" data-bb-img="images/foo.png">My Button</div>
```
A BlackBerry 10 or PlayBook button can be styled in one of the following ways:

* **Text Only:** _(Text is centered)_
* **Image + Text:** _(Image &amp; Text are left justified)_
* **Image Only:** _(Image is centered and button is shrunk to fit image)_

BlackBerry 10 and PlayBook Button Image Sizes

* BlackBerry PlayBook - 29 x 29 pixels
* BlackBerry 10 - 71 x 71 pixels


## JavaScript Interface
The following JavaScript interfaces are available for dynamically manipulating a Button after the screen has been added to the DOM

### Dynamic Styling
A button can be created dynamically to be inserted into a screen that is already in the live DOM (after the ondomready event has fired for the screen).  This allows you to dynamically create buttons on the fly based on user interaction.  This is accomplished by using the **bb.button.style()** function.

```javascript
// Create the element just like you would in a normal screen declaration
var button = document.createElement('div');
button.setAttribute('data-bb-type','button');
button.setAttribute('data-bb-style', 'stretch');
button.innerHTML = 'Click Me To Remove';
button.onclick = function() {
		this.remove();
	};

// Apply our styling
button = bb.button.style(button);

// Insert it into the screen and update the scroller
document.getElementById('buttonContainer').appendChild(button);
bb.refresh();
```
### show() and hide()

When you want to dynamically show or hide your button you can call it&apos;s **show()** and **hide()** functions.

```javascript
	document.getElementById('plainBtn').show();
	document.getElementById('plainBtn').hide();
```

### remove()

As a convenience you can also remove your button from the screen by calling the **remove()** function.

```javascript
	document.getElementById('plainBtn').remove();
```

### enable() and disable()

You can disable in your Button by adding the **data-bb-disabled="true"** attribute.  When you want to dynamically change the state of your button you can call it&apos;s **enable()** and **disable()** functions.

```javascript
	document.getElementById('plainBtn').enable();
	document.getElementById('plainBtn').disable();
```

### getCaption() and setCaption(value)

The **getCaption()** and **setCaption(value)** functions have been added to buttons to allow you to get/set their caption for all OS versions
```javascript
document.getElementById('plainBtn').setCaption('my caption');
alert(document.getElementById('plainBtn').getCaption());
```

### getImage() and setImage(value)

The **getImage()** and **setImage(value)** functions have been added to buttons to allow you to get/set their image.  This is only supported on BlackBerry 10 and PlayBook styling
```javascript
document.getElementById('plainBtn').setImage('images/foo.png');
alert(document.getElementById('plainBtn').getImage());
```

