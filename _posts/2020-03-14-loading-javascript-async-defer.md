---
layout: post
title: Loading JavaScript using async and defer
---

Inline scripts and links to external JavaScript files are commonly placed before the closing `</body>` tag so that they will be loaded and executed only after the HTML is parsed.

For the links to external JavaScript files, however, the `defer` and `async` attributes can be added. If either attribute is added to the opening `<script>` tag, e.g., `<script defer>` or `<script async>`, the script tag should be placed inside the `<head></head>` section and not before the closing `</body>` tag. Otherwise, either attribute will not work.

## defer

The `defer` attribute will load the script asynchronously while the HTML is being parsed. After the HTML is parsed, the script will then execute. This is like placing the script tag before the closing `</body>` tag (as mentioned before) but a little bit faster since the script is already loaded when the HTML is parsed and all it has to do is execute.

![defer](https://raw.githubusercontent.com/kennyalmendral/kennyalmendral.github.io/master/images/defer.png "defer")

## async

The `async` attribute will load the script asynchronously while the HTML is being parsed and when the script is ready, the HTML parsing is paused for the script to execute. When the execution is done, the HTML parsing is resumed.

![async](https://raw.githubusercontent.com/kennyalmendral/kennyalmendral.github.io/master/images/async.png "async")

## Notes

- Scripts with the `defer` attribute are executed in the order which they are defined in the HTML markup while scripts with the `async` attribute are executed in an irregular order, when they become available.

- The `async` attribute blocks the parsing of the page while the `defer` attribute does not and if you add both to a script tag that points to the same external JavaScript file, e.g.,

	```html
	<script src="app.js" async></script>
	<script src="app.js" defer></script>
	```

	The script tag with the `async` attribute will take precedence on modern browsers while older browsers will fall back to `defer`.
