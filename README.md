﻿Svidget.js
==========

Svidget.js (SVG + widget) is a robust and powerful framework for building complex data visualization widgets in SVG. 

Svidget is not another data visualization framework like [D3](https://github.com/mbostock/d3) or [SnapSVG](https://github.com/adobe-webplatform/Snap.svg). Rather, it is a framework for componetizing your data visualizations and exposing it as a widget to use you any HTML5 page. As a matter of fact, you can combine Svidget.js with D3 or any popular visualization framework, provided it can be embedded directly into an SVG file (see Compatibility below). Best of all, it is endorsed by Chuck Norris!*

<small>\* Just kidding</small>

> Svidget is currently under active development. Although it is functionally complete and stable, expect issues. I am currently rewriting all the tests, finalizing the documentation, and working on some demos. Check here often for updates.

###Download
Download the latest stable builds from the `dist` folder.


###Using
To get started, consider this simple star SVG file.

![Star](data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiID8+CjxzdmcgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgeG1sbnM6c3ZpZGdldD0iaHR0cDovL3d3dy5zdmlkZ2V0Lm9yZy9zdmlkZ2V0IgoJCSB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCI+Cgk8dGl0bGU+U3RhcjwvdGl0bGU+CgkKCTxkZWZzPgoJCTxsaW5lYXJHcmFkaWVudCBpZD0iYmFja2dyb3VuZEdyYWRpZW50IiB5MT0iMCIgeTI9IjEwMCUiIHgxPSIwIiB4Mj0iMCI+CgkJCTxzdG9wIG9mZnNldD0iMCUiIHN0b3AtY29sb3I9IiNmZmYiIHN0b3Atb3BhY2l0eT0iMC41IiAvPgoJCQk8c3RvcCBvZmZzZXQ9IjEwMCUiIHN0b3AtY29sb3I9IiNmZmYiIHN0b3Atb3BhY2l0eT0iMC4wIiAvPgoJCTwvbGluZWFyR3JhZGllbnQ+Cgk8L2RlZnM+CgoJPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMCA4KSI+CgkJPHBhdGggaWQ9InN0YXJiYWNrIiBmaWxsPSJjb3JuZmxvd2VyYmx1ZSIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSI2IiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNIDEwMCA0IEwgMTI4LjIxNCA2MS4xNjcyIEwgMTkxLjMwMSA3MC4zMzQ0IEwgMTQ1LjY1MSAxMTQuODMzIEwgMTU2LjQyNyAxNzcuNjY2IEwgMTAwIDE0OCBMIDQzLjU3MjYgMTc3LjY2NiBMIDU0LjM0OTMgMTE0LjgzMyBMIDguNjk4NTcgNzAuMzM0NCBMIDcxLjc4NjMgNjEuMTY3MiBaIiAvPgoJCTxwYXRoIGlkPSJzdGFyZnJvbnQiIGZpbGw9InVybCgjYmFja2dyb3VuZEdyYWRpZW50KSIgc3Ryb2tlPSJtaWRuaWdodGJsdWUiIHN0cm9rZS13aWR0aD0iNiIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTSAxMDAgNCBMIDEyOC4yMTQgNjEuMTY3MiBMIDE5MS4zMDEgNzAuMzM0NCBMIDE0NS42NTEgMTE0LjgzMyBMIDE1Ni40MjcgMTc3LjY2NiBMIDEwMCAxNDggTCA0My41NzI2IDE3Ny42NjYgTCA1NC4zNDkzIDExNC44MzMgTCA4LjY5ODU3IDcwLjMzNDQgTCA3MS43ODYzIDYxLjE2NzIgWiIgLz4KCTwvZz4KCjwvc3ZnPg==)

And here's its SVG:
```xml
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="200" height="200">
	<defs>
		<linearGradient id="backgroundGradient" y1="0" y2="100%" x1="0" x2="0">
			<stop offset="0%" stop-color="#fff" stop-opacity="0.5" />
			<stop offset="100%" stop-color="#fff" stop-opacity="0.0" />
		</linearGradient>
	</defs>
	<g transform="translate(0 8)">
		<path id="starback" fill="cornflowerblue" stroke="white" stroke-width="6" stroke-linejoin="round" d="M 100 4 L 128.214 61.1672 L 191.301 70.3344 L 145.651 114.833 L 156.427 177.666 L 100 148 L 43.5726 177.666 L 54.3493 114.833 L 8.69857 70.3344 L 71.7863 61.1672 Z" />
		<path id="starfront" fill="url(#backgroundGradient)" stroke="midnightblue" stroke-width="6" stroke-linejoin="round" d="M 100 4 L 128.214 61.1672 L 191.301 70.3344 L 145.651 114.833 L 156.427 177.666 L 100 148 L 43.5726 177.666 L 54.3493 114.833 L 8.69857 70.3344 L 71.7863 61.1672 Z" />
	</g>
</svg>
```


Ok, thats great. But what if I want to add interactivity to this SVG document. Maybe I want to change its colors. And, I want to provide a way for a user to spin it. Oh, and I want to be notified when it's done spinning. 

The brute force approach would be to embed the SVG directly into the HTML, and write my script to manage user interaction and notifications. In the process, I would have interminged SVG with HTML and JavaScript, and that gets messy in a hurry. 

With Svidget, you componentize your UI and its logic as a widget in a SVG file.

```xml
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" 
xmlns:svidget="http://www.svidget.org/svidget"
width="200" height="200">

<svidget:params>
	<svidget:param name="borderColor" shortname="bd" type="string" subtype="color" binding="#starfront@stroke" />
	<svidget:param name="borderWidth" shortname="bw" type="number" binding="#starfront@stroke-width,#starback@stroke-width" />
	<svidget:param name="backgroundColor" shortname="bg" type="string" subtype="color" binding="#starback@fill" />
</svidget:params>

<svidget:actions>
	<svidget:action name="spin" external="true" binding="spin" description="Spins the star.">
		<svidget:actionparam name="power" type="number" default="5" description="The amount of power to exert on the star to begin its rotation."  />
	</svidget:action>
</svidget:actions>

<svidget:events>
	<svidget:event name="spinComplete" description="Triggered for a mouse over or touch hover on the shape." />
</svidget:events>

<script type="application/javascript" xlink:href="../scripts/svidget.js"></script>

<defs>
...
<!-- rest of SVG widget -->
```

There are 3 artifacts to a widget: **params**, **actions**, and **events**. 

> **Params** - these are the data endpoints. They can be read from and set at any point during the widget's lifecycle.

> **Actions** - these are your action endpoints (aka methods). They are abstractions to underlying functionality in the widget. They can represent a single function, mutliple functions, or nothing at all.

> **Events** - these represent notifications from the widget. In addition to these, params and actions also have events when they are set or invoked.


Ok so now that we have an SVG widget, let's use it on a page:

```html
<object id="star" role="svidget" data="widgets/star.svg" type="image/svg+xml" width="200" height="200">
	<param name="borderColor" value="darkgreen" />
	<param name="backgroundColor" value="green" />
	<param name="borderWidth" value="10" />
</object>
```

That's it! In addition to this declarative syntax, you can also programatically add a widget to the page at any time:

```javascript
svidget.load("#widgetContainer", "widgets/star.svg", { 
	borderColor: "orange", 
	backgroundColor: "green",
	borderWidth: 10 
});
```

For more information, see the Wiki page. Svidget website coming soon.



###Compatibility
These frameworks have been tested and shown to play nice with Svidget within an SVG file.

> - jQuery 2.x and above
> - D3.js
> - svg.js
> - snap.svg

Basically any JavaScript framework that can be embedded in an SVG file will work. 
A general rule is if the framework only supports IE9 and above it will work. Frameworks that try to support non-HTML5 browsers like IE6 probably won't.


####Falling Back
In non-HTML5 browsers, Svidget will attempt to fall back to fallback content specified in the <object> tag.


###Build
The latest builds are in the releases folder. Get started today! Please note that Svidget is in beta (current version 0.1.0), so the API may change without notice.

When reporting issues, please be as descriptive as possible, including steps to reproduce.

If you want to build it yourself, clone the project then follow these steps:

Install the Grunt CLI:

    npm install -g grunt-cli

Run this grunt command:

    grunt all


###Contribute
If you find Svidget fascinating and want to contribute, that's great! Please follow these guidelines:

- Please respect the coding conventions in place. Put a comment as to what you changed. Don't worry, comments get stripped out during the build. 
- Please do some basic testing of your code, including testing every button on the kitchen sink page. (unit tests coming soon)


###License
Licensed under [MIT](http://opensource.org/licenses/MIT).


