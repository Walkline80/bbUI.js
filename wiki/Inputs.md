All standard HTML5 inputs are supported by bbUI.  However some of these inputs have special handling on BlackBerry 10 to create the same native user experience.  The details of this special handling is outlined below.

## BlackBerry 10 Text Input 
![Input](images/screenshots/inputWithClear.png)

When creating an input of type **text, password, tel, url, email, number, search** for BlackBerry 10, the bbUI framework will automatically add a "clear" button to the end of the input when the user sets focus to the control.  

You can remove this clear button (except for an input of type "search") by adding the **data-bb-clear="none"** attribute for your input.

```html
<input type="text" value="Hello World" data-bb-clear="none"/>
```

## BlackBerry 10 File Input

When you declare an input of type "file", bbUI will create a browse button which will launch the file picker.  When a file is returned, the file name will be displayed as the caption of the button.  You can specify a caption to appear on the file browse button by specifying a **data-bb-caption** attribute.  This will help with localizing your application.  If no **data-bb-caption** attribute is specified, then the English "Choose File" text will appear.

```html
<input id="hi" data-bb-caption="hello world" type="file"/>
```

## JavaScript Interface

The JavaScript interface is only provided on BlackBerry 10 styling of controls.  This is needed for BlackBerry 10 because of the specific user interactions that are provided with some of the controls.  For other operating systems standard input JavaScript interfaces can be used.

The list of inputs that receive this JavaScript interface on BlackBerry 10 are: **text, password, tel, url, email, number, date, time, datetime, month, datetime-local, color, search**

### Dynamic Styling

An input can be created dynamically to be inserted into a screen that is already in the live DOM (after the ondomready event has fired for the screen).  This allows you to dynamically create inputs on the fly based on user interaction.  This is accomplished by using the **bb.textInput.style()** function.

```javascript
// Create the element just like you would in a normal screen declaration
var input = document.createElement('input');
input.setAttribute('type','text');
input.setAttribute('value', 'My Text');
input.onchange = function() {
		// Do something
	};

// Apply our styling
input = bb.textInput.style(input);

// Insert it into the screen and update the scroller
document.getElementById('inputContainer').appendChild(input);
bb.refresh();
```

### show() and hide()

When you want to dynamically show or hide your input you can call it&apos;s **show()** and **hide()** functions.

```javascript
document.getElementById('myinput').show();
document.getElementById('myinput').hide();
```

### remove()

As a convenience you can also remove your input from the screen by calling the **remove()** function.

```javascript
document.getElementById('myinput').remove();
```

### enable() and disable()

You can disable in your input by adding the standard **disabled="true"** attribute.  When you want to dynamically change the state of your input you can call it&apos;s **enable()** and **disable()** functions.

```javascript
document.getElementById('myinput').enable();
document.getElementById('myinput').disable();
```
