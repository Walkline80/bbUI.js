From experimenting with the platform I've been able to figure out a few "Pro Tips" for those who are looking to squeeze out as much performance as possible from their applications using bbUI.  Below you will find some of them.

## onscreenready vs ondomready
When the scenario arises where you need to manipulate a screen's content when it is being loaded for the user via **bb.pushScreen()** you have the options of using _onscreenready_ or _ondomready_ [loading events](https://github.com/blackberry/bbUI.js/wiki/Toolkit-Initialization). For the absolute best performance in a screen you should manipulate the DOM of the screen in the **onscreenready** event.  This will allow you to manipulate the screen before it is rendered and added into the DOM.

When should you use **ondomready**?  These are scenarios where you are loading in remote content, or content that will take _significant time_ to load. You want to ensure that when a user requests to open a new screen that it opens very quickly.  If you have significant processing to do, you won't want to do this in the onscreenready event because it will delay the initial showing of the screen.

When using **ondomready** you should create a screen that uses the built in [Activity Indicator functionality of a Screen](https://github.com/blackberry/bbUI.js/wiki/Screens) which will draw an animation on the screen while you are processing your data in the _ondomready_ event.

## Background Images For Screens
I've found that if you use a background image that you tile across the screen it will dramatically reduce your animation speed for screen transitions.  By using a solid color or gradient animations will be smooth.  The tiling of the image while it is loading tends to make the animation choppy

## Image Lists
If you are loading in larger images that are being scaled into your image list, or retrieving remote images for your list, I would recommend using the **data-bb-image-effect="fade"** attribute for your image list.  

```html
<div data-bb-type="image-list" data-bb-image-effect="fade">
  
</div>
```

This will ensure that the screen will appear and animate very quickly and the loading of the images will not make the animations choppy.  It also ensures that the images have a nice fade effect once they have been loaded.