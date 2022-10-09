---
toc: false
title: "Javascriptda minimal router."
description: "Javascriptda dasturlash tili muhitida minimal router."
keywords: "javascript, route, router, ilova, havola, harakat"
---

1. test.html 

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>Router tester</title>
</head>
<body>
	<table border="1" width="40%">
		<thead>
			<th>Router</th>
			<th>Havola</th>
		</thead>
		<tbody>
			<tr>
				<td> <code>"/home": "index"</code> </td>
				<td><a href="app://home">app://home</a></td>
			</tr>
			<tr>
				<td> <code>"/news/:id": "news"</code> </td>
				<td><a href="app://news/123">app://news/123</a></td>
			</tr>
		</tbody>
	</table>
	<script type="text/javascript" src="app.js"></script>
</body>
</html>
```
2. app.js

```js
var Router = {
	routes: {
		"/": "index",
		"/home": "index",
		"/news/:id": "news"
	},
	init: function() {
		this._routes = [];
		for (let route in this.routes) {
    		let method = this.routes[route];
    		this._routes.push({
        		pattern: new RegExp('^' + route.replace(/:\w+/g, '(\\w+)') + '$'),
        		callback: this[method]
    		});
		}
	},
	dispatch: function(path) {
		var i = this._routes.length;
		while (i--) {
    		var args = path.match(this._routes[i].pattern);
    		if (args) {
        		this._routes[i].callback.apply(this, args.slice(1));
    		}
		}
	},
	index: function() {
		alert('Home');
	},
	news: function(name) {
		alert(`NewsId: ${name}`);
	}
}

var checkProtocol = (url) => {
	if (typeof url == undefined || url == null) {
    	return false;
	}

	let test = /^app:\/\/(.+)$/.test(url)
	if (test) {
    	return '/' + url.match(/^app:\/\/(.+)$/)[1];
	}

	return false;
}

var runApp = () => {
	Router.init();
	var Anchors = document.getElementsByTagName("a");
	for (var i = 0; i < Anchors.length ; i++) {
		let match = checkProtocol( Anchors[i].href );
		if ( match ) {
			Anchors[i].addEventListener("click", function (event) {
				Router.dispatch( match );
				event.preventDefault();
			}, false);
		}
	}
}

runApp();
```