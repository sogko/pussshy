# Pussshy
 Pussshy is a forked version of [Christopher Yee's Pushy](https://github.com/christophery/pushy/), a responsive off-canvas navigation menu using CSS transforms & transitions.

It has been re-written to include several new modern features thats going to make you web application more robust. 

## Features
New and modern features included in this version:

* Bi-directional.
* Supports multiple menus and multiple canvasses.
* Custom class targets.
* CommonJS-ready for your [browserify](http://browserify.org/)-ing needs  <br/> (exported to both `window` and `module` exports).
* Included source SASS (.scss) files for you to easily customise it to your project needs.

Plus all the goodness from [the original version](https://github.com/christophery/pushy/):

* Uses CSS transforms & transitions.
* Smooth performance on mobile devices.
* jQuery animation fallback for IE 7 - 9.
* Responsive.


## Requirements
* jQuery v1.11.x and above

For list of supported browsers, see [Browser support](#browser-support).


## Quickstart
1. Download Pussshy using one of the two methods
	* using [Bower](http://bower.io): <br/>```bower install pussshy```
	* directly from [packaged source](https://github.com/sogko/pussshy/archive/master.zip).
	
2. Include jQuery and Pussshy assets in your HTML.
<br/>Note: jQuery script has to come before `pussshy.min.js`
    ```html
    <link rel="stylesheet" href="{path-to-src}/pussshy.min.css"/>
    
    <script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
    <script src="{path-to-src}/pussshy.min.js"></script>
    
    ```
3. Add the following markup in your HTML to define [the four  (4) Pussshy components](#components)

    ```html
<!-- Pussshy off-canvas menu and its menu-items -->
<div class="pussshy__menu">
	<ul class="pussshy__menu-items">
		<li><a href="#">Menu item 1</a></li>
		<li><a href="#">Menu item 2</a></li>
		<li><a href="#">Add more items</a></li>
	</ul>
</div>

<!-- Pussshy content canvas --->
<div class="pussshy__canvas">
	<!-- insert content here -->
	<h1>Pussshy Demo</h1>
	
	<!-- include the Pussshy menu-button somewhere -->
	<button class="pussshy__menu-button">Show menu</button>
	
	<!-- more content here -->
	<p>Ipsum lorem and all that</p>
	<p>Ipsum lorem and all that</p>
	<p>Ipsum lorem and all that</p>
	<p>Ipsum lorem and all that</p>
</div>
    ```

4. Create a Pussshy instance
    ```html
<script>
	$(document).ready(function () {
		var opts = {}; // use default options
		var p = new Pussshy(opts);
	});
</script>
    ```

5. Done!

## API
### Components
Pussshy requires the following HTML components to work:

#### Content canvas
Class name: ```pussshy__canvas```

The content canvas contains content that will be moved off-canvas when the menu is active.

You can have multiple canvasses for each Pussshy instances. 

#### Off-canvas menu
Class name: ```pussshy__menu```

This is the menu that will start off from outside of the content canvas.

#### Menu items
Class name: ```pussshy__menu-items```

Menu items should be defined within ```pussshy__menu```.

#### Menu button
Class name: ```pussshy__menu-button```

Menu button will bring up the menu when clicked.

#### Overlay
Class name: ```pussshy__site-overlay```

The overlay that covers the content canvas when the menu is active.

Note:
* The overlay component is optional and will be created automatically if its not defined.
* Its the only component not required to be contained within the specified HTML context (i.e. its within global context)

----

### Options
You can pass in options into the object constructor to override default options and CSS targets.

For e.g.
```javascript
var opts = {
	direction: 'right',
	...
};
var p = new Pussshy(opts);
...
```
#### direction
Set the direction from which the off-canvas will move when shown.

Default: `left`.
Possible values: `left` | `right`.

#### canvasTarget
Set the CSS selector for the [content canvas component](#content-canvas).

Default: `.pussshy__canvas`
Possible values: Valid CSS selector.

#### menuTarget
Set the CSS selector for the [off-canvas menu component](#off-canvas-menu).

Default: `.pussshy__menu`
Possible values: Valid CSS selector.

#### menuItemsTarget
Set the CSS selector for the [menu items component](#menu-items).

Default: `.pussshy__menu-items`
Possible values: Valid CSS selector.

#### menuButtonTarget
Set the CSS selector for the [menu button component](#menu-button).

Default: `.pussshy__menu-button`
Possible values: Valid CSS selector.

#### siteOverlayTarget
Set the CSS selector for the [overlay component](#overlay).

This is only needed if you are defining your own overlay.

Typically, it is **not necessary to change** the `siteOverlayTarget` value.

Default: `.pussshy__site-overlay`.
Possible values: Valid CSS selector.

#### contextTarget
Set the CSS selector for the context.

The context should contain [the four (4) main Pussshy components](#components).

Typically, it is **not necessary to change** the `contextTarget` value.

Default: `body`
Possible values: Valid CSS selector.

----

### Object methods
#### p.toggle()
Toggles (hide/show) the menu programmatically.

For e.g.
```javascript
// create a Pussshy instance
var p = new Pussshy(opts);
...
// toggle Pussshy menu
p.toggle();
...
```

----

## Examples
For more examples, see the [`Examples`](examples) folder


## Browser support
| Browser | CSS [3d transforms](http://caniuse.com/#feat=transforms3d) & [transitions](http://caniuse.com/#feat=css-transitions) | [jQuery animation](http://jquery.com/browser-support/) |
| ------- | ---------------------------- | ---------------- |
| Internet Explorer | 10+  | 6+ for jQuery 1.x, 9+ for jQuery 2.x |
| Firefox | 31+  |  31+ |
| Google Chrome | 31+  |  31+ |
| Safari | 5.1+  |  5.1+ |
| iOS Safari | 7.1+  | 6.1+ |
| Opera | Unknown  | 12.1x |
| Opera Mini | Not supported  | Unknown |
| Android Browser | 4.0+  | 2.3, 4.0+ |
| Chrome for Android | 38  | Unknown |

## Changelog

| Release  |  Date    | Notes  |
| :--------| :------- | :----- |
| -    | - | Still under development |


## License

Copyright (c) 2014 Hafiz Ismail. This software is licensed under the [MIT License](https://github.com/sogko/pussshy/raw/master/LICENSE).
