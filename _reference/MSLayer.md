---
title: MSLayer
summary: MSLayer is the base class that represents a layer object.
rels:
  - MSLayerGroup
  - MSRect
  - GKRect
  - MSStyle
  - MSPage
  - MSShapeGroup
---

MSLayer is the base class that represents a layer object.

## Methods & Attributes

### frame: (readonly)

An instance of [MSRect](/reference/MSRect/). Determines size and position on the canvas.

### style: (readonly)

An instance of [MSStyle](/reference/MSStyle/). Determines all style-related attributes such as Borders, Fills, Shadows and more

### name: setName:(NSString)name

Get /set the name of the layer, as it appears in the layer list.

### isVisible:, setIsVisible:(BOOL)value

Get / set the layer's visibility. Returns `true` if the layer is visible, and `false` if it is hidden.

To **hide** a layer, do:

```javascript
layer.setIsVisible(false)
```

If you want to toggle a layer’s visibility, do:

```javascript
layer.setIsVisible(!layer.isVisible())
```


### isLocked:, setIsLocked:(BOOL)value

Returns `true` if the layer is locked, and `false` if it isn’t locked.

To **lock** a layer, do:

```javascript
layer.setIsLocked(true)
```

If you want to toggle a layer’s lock status, do:

```javascript
layer.setIsLocked(!layer.isLocked())
```

### rotation:, setRotation:(CGFloat)newRotation

Get / set layer rotation, in degrees.

### isFlippedHorizontal:, setIsFlippedHorizontal:(BOOL)isFlippedHorizontal, isFlippedVertical:, setIsFlippedVertical:(BOOL)isFlippedVertical

Flips the layer horizontally or vertically.

```javascript
layer.isFlippedHorizontal()
```

### parentGroup:

Returns the parent group of this layer. Note that this can return an [MSPage](/reference/MSPage/) or [MSArtboardGroup](/reference/MSArtboardGroup/) as well as an [MSLayerGroup](/reference/MSLayerGroup/)

### isSelected:, setIsSelected:

True if the layer is selected, false otherwise.

### select:byExpandingSelection:

Check the [Working with Selections](/code-examples/working-with-selections/) section for some examples.

### absoluteRect: (readonly)

Returns a [MSAbsoluteRect](/reference/MSAbsoluteRect/) object that returns the bounds of this layer in absolute coordinates; it takes into account the layer’s rotation and that of any of its parents.

### duplicate:

Duplicates the layer and insert the copy above itself.

### userInfo:

Returns a dictionary of metadata keys and values, if they have been using the corresponding methods in [MSPluginCommand](/reference/MSPluginCommand/) (`setValue:forKey:onLayer:` or `setValue:forKey:onLayer:forPluginIdentifier:`)
