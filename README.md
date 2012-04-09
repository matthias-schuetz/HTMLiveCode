HTMLiveCode
===========

## A browser-based editor for real-time HTML/CSS/JS prototyping

HTMLiveCode is a simple editor which is built on top of HTML, CSS and JavaScript. It was made for the editing of these languages and can be used for rapid prototyping. The editor can be customized in its appearance so there are themes and some other editor options. HTMLiveCode is based on CodeMirror and makes use of JSLint and HTML5's localStorage.

<img src="http://matthias-schuetz.github.com/htmlivecode/htmlivecode.png" />

## Demo
<a href="http://htmlivecode.com/">Click here for a live demonstration.</a>

## Usage

After loading all necessary files of the folders "js" and "css" in your main file, HTMLiveCode is available in the global namespace and must be instantiated as an object. You don't need any HTML markup as the editor will be attached to the &lt;body&gt; element. You don't need to specify any options since HTMLiveCode can be started with default settings. The editor should be instantiated when the DOM is ready. For example, use the "DOMContentLoaded" event to make sure that everything has been loaded.

### Defaults

```javascript
/*
 * HTMLiveCode instantiation (all arguments are optional)
 * 
 * @param Object settings Object which contains all options
 *        settings:
 *        @param Boolean gutter Toggles gutter and line numbers
 *        @param Boolean wordWrap Toggles word wrapping
 *        @param String theme Sets color theme (either "bright" or "dark")
 *        @param String imageProxyPath Only works when HTMLiveCode is used locally!
 *                      Virtual path prefix for CSS and IMG urls
 *                      (e.g. "C:/Images/") so you can set a "background-image" url
 *                      to "button.png" and it will virtually be routed to
 *                      "file:///C:/Images/button.png"
 */

var liveEditor = new HTMLiveCode(settings);
```

### Examples

```javascript
// Default settings
window.addEventListener("DOMContentLoaded", function() {
	window.liveEditor = new HTMLiveCode();
	window.liveEditor.init();
});

// Custom options
window.addEventListener("DOMContentLoaded", function() {
	window.liveEditor = new HTMLiveCode({
		gutter: false,
		wordWrap: false,
		theme: "dark",
		imageProxyPath: "C:/Images/" // only works when HTMLiveCode is used locally
	});
	window.liveEditor.init();
});
```

## Shortcuts
HTMLiveCode comes with some default shortcuts:

* **ALT-M:** Toggle menu bar
* **ALT-T:** Toggle theme
* **ALT-I:** Increase font size
* **ALT-O:** Decrease font size
* **ALT-0:** Reset font size
* **ALT-G:** Toggle gutter
* **ALT-W:** Toggle word wrap

## Notes
* **Compatibility:** HTMLiveCode was developed with HTML5 in mind. So it works in modern browsers and Internet Explorer from version 9 on.

## License

HTMLiveCode is released under the MIT license.