---
description: Fixed lists & grids used for different layout options.
---

# Lists / Grids

### Fixed List

The fixed list widget will take a number of components and display them in a vertical list.

The `mainAxisAlignment` property supports the following options: `start`, `end`, `spaceBetween`, `spaceAround` & `spaceEvenly`.

The `crossAxisAlignment` property supports the following options: `start`, `end`, `center`, `stretch` & `baseline`.

Both `mainAxisAlignment` & `crossAxisAlignment` are optional.

```javascript
{
	"type": "fixedListWidget",
	"mainAxisAlignment": "start",
	"crossAxisAlignment": "center",
	"components": [{},{}]
}
```

### Fixed Horizontal List

The fixed horizontal list widget will take a number of components and display them in a horizontal list.

The `mainAxisAlignment` property supports the following options: `start`, `end`, `spaceBetween`, `spaceAround` & `spaceEvenly`.

The `crossAxisAlignment` property supports the following options: `start`, `end`, `center`, `stretch` & `baseline`.

Both `mainAxisAlignment` & `crossAxisAlignment` are optional.

```javascript
{
	"type": "fixedHorizontalListWidget",
	"mainAxisAlignment": "start",
	"crossAxisAlignment": "center",
	"components": [{},{}]
}
```

### Fixed Horizontal Scroll List

The fixed horizontal list scroll widget will take a number of components and display them in a horizontal list with scrolling. All properties in this component are required.

```javascript
{
	"type": "fixedHorizontalListScrollWidget",
	"height": 150,
	"components": [{},{}]
}
```

### Fixed Grid

The fixed grid widget can be used to take a specified number of components and display them on a grid. The `itemPadding` property is used to add a padding between the items and is optional. `childAspectRatio` defaults to 1.0 when unspecified.

```javascript
{
	"type": "fixedGridWidget",
	"itemPadding": "xs",
	"columns": 2,
	"childAspectRatio": 1.5,
	"components": [{},{}]
}
```
