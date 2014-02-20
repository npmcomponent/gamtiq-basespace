*This repository is a mirror of the [component](http://component.io) module [gamtiq/basespace](http://github.com/gamtiq/basespace). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/gamtiq-basespace`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# basespace

Functions to create namespaces inside objects.

## Installation

### Node

    npm install basespace

### Component

    component install gamtiq/basespace

### Jam

    jam install basespace

### Bower

    bower install basespace

### AMD, script tag

Use `dist/basespace.js` or `dist/basespace.min.js` (minified version).

## Usage

### Node, Component

```js
var ns = require("basespace");
...
```

### Jam

```js
require(["basespace"], function(ns) {
    ...
});
```

### AMD

```js
define(["path/to/dist/basespace.js"], function(ns) {
    ...
});
```

### Bower, script tag

```html
<!-- Use bower_components/basespace/dist/basespace.js if the library was installed via Bower -->
<script type="text/javascript" src="path/to/dist/basespace.js"></script>
<script type="text/javascript">
    // basespace is available via basespace field of window object
    var ns = basespace;
    ...
</script>
```

## Example

```js
var app = {
    space: ns.space
};
ns(["model", "ui.dialog", "ui.list", "ui.list.cyclic", "util"], app);
app.space("ui.menu", "template");
app.space("data").util = {...};
```

## API

### ns(namespaces: Array|String, [context: Object], [value])

Create specified `namespaces` inside `context` if they do not exist.
`context` is global object (i.e. `window` in browser) by default.
`value` specifies a value that will be assigned to a final field. `{}` by default.

Return the value for the last of created names/fields.

### .space(namespace: String, ...)

Create the specified `namespace` inside `this` object.

Return the value for the last of created names/fields.

## Licence

MIT
