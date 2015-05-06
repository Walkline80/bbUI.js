To initialize bbUI you need to call the **bb.init()** function before you start loading UI elements into your application. **THIS IS MANDITORY**  The bb.int() function takes one parameter which is a JavaScript object containing any of the options you wish to override.  If you want to simply use the default configuration call the initialization function with no parameters _bb.init()_. 

## Simplest Initialization

The easiest and simplest way to initialize your application with bbUI is shown in the following code.  The code assumes that you are using the **cordova.js** file path used with the BlackBerry 10 WebWorks SDK 2.0.  By including this file reference it will ensure that the **deviceready** event will fire.  This ensures that the entire WebWorks framework is loaded before opening your first screen.

More information on application structure and pushing screens [can be found here](Application-Structure)

```html
    <html>
        <head>
            <link  rel="stylesheet" type="text/css" href="bbui.css"></link>
            <script type="text/javascript" src="bbui.js"></script>
            <script type="text/javascript" src="cordova.js"></script>
            <script type="text/javascript">
            window.addEventListener('load',function() {
                document.addEventListener('deviceready', function(e) {
                    bb.init();
                    // Open our first screen
                    bb.pushScreen('firstScreen.htm', 'firstScreen');
                }, false);
            }, false);
            </script>
        </head>
        <body>
        </body>
    </html>
```


## Default Options which can be Overridden 

The default values of the options which can be overriden are:
```javascript
    {
        onbackkey: null,                   // Custom handler for back key on BlackBerry 5/6/7 smartphones
        onscreenready: null,               // Manipulate your screen before it's inserted into the DOM
        ondomready: null,                  // Manipulate your screen after it's inserted into the DOM
        coloredTitleBar: false,            // If set to true, the title bar will be colored based on the highlight color
        controlsDark: false,               // If set to true, the controls will use the dark theme
        listsDark: false,                  // If set to true, lists will use the dark theme (you need a dark background)
        highlightColor: '#00A8DF',         // A highlight color to use when a user selects an item   
    }
```

Here's an example of what an bb.init() call may look like with some overriden values:
```javascript
bb.init({controlsDark: true, listsDark: false, bb10ForPlayBook: true});

```


## Ready Events

You can be notified when your screen, and all associated &lt;script&gt; tags, are loaded and ready for manipulation before styling is applied using the **onscreenready** event.  The screen is still not 
contained in the DOM of the page at this point, but can be manipulated to modify its contents before the bbUI styling is applied. This allows you to perform your data manipulation **before** the screen has
been displayed to the user and minimizes rendering engine layouts which are very expensive.

_NOTE: If you are using jQuery to select DOM elements to manipulate, you must wait until after the ondomready event fires_

You can also be notified when your screen, and all associated &lt;script&gt; tags, have been inserted into the DOM using the **ondomready** event.  This allows you to perform your data manipulation **after** 
the screen has been displayed to the user.

When using ondomready, you need to understand that there are situations where you need to use this, but it will come with a performance hit.  By manipulating the content of the screen after it is loaded into the DOM your user interface performance will be impacted.

To subscribe to this event simply assign a function to the **onscreenready** parameter of the init function.  The function will be called with the DOM element of your screen, and 
the id you have specified for that screen so that you can apply any screen specific changes.

Since all of the script files for the specific screen are loaded before the **onscreenready** or **ondomready** events are fired, you can place all your screen specific logic in those files
and only have one **onscreenready** and **ondomready** global handler to act as the "traffic cop".

When either the onscreenready or ondomready events fire, they will be passed three parameters:
* The **DOMElement** of the screen which was loaded
* The **id** of the screen which the the DOMElement belongs
* The optional **params** object passed into the bb.pushScreen() function

The **getElementById()** function has been added to the element object that is passed into **onscreenready** and **ondomready** events so that you can manipulate the DOM of the element passed into the event.
```html
    <html>
        <head>
            <link  rel="stylesheet" type="text/css" href="bbui.css"></link>
            <script type="text/javascript" src="bbui.js"></script>
            <script type="text/javascript" src="cordova.js"></script>
            <script type="text/javascript">
            window.addEventListener('load',function() {
                document.addEventListener('deviceready', function(e) {
                    bb.init({onscreenready : function(element, id, params) {
                             if (id == 'menu') {
                                 doMenuLoadingBeforeInsert(element, params);
                            } 
                         },
                         ondomready: function(element, id, params) {
                             if (id == 'menu') {
                                 doMenuLoadingAfterInsert(element, params);
                            } 
                         }});
                    // Open our first screen
                    bb.pushScreen('menu.htm', 'menu');
                }, false);
             }, false);
            </script>
        </head>
        <body>
        
        </body>
    </html>
```