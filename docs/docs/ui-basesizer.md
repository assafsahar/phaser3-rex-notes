## Introduction

Base class of all ui plugins.

- Author: Rex

## Usage

### Minimum size

```javascript
sizer.setMinSize(width, height);
```

or

```javascript
sizer.setMinWidth(width);
sizer.setMinHeight(height);
```

### Bounds of sizer

- Get
    ```javascript
    var leftBound = sizer.left;
    var rightBound = sizer.right;
    var topBound = sizer.top;
    var bottomBound = sizer.bottom;
    ```
- Set
    ```javascript
    sizer.left = leftBound;
    sizer.right = rightBound;
    sizer.top = topBound;
    sizer.bottom = bottomBound;
    ```
    or
    ```javascript
    sizer.alignLeft(leftBound);
    sizer.alignRight(rightBound);
    sizer.alignTop(topBound);
    sizer.alignBottom(bottomBound);
    ```

### Push into bounds

Align sizer to bound if overlapping it.

```javascript
sizer.pushIntoBounds();
```

or

```javascript
sizer.pushIntoBounds(bounds);
```

- `bounds` : Bounds in [rectangle object](geom-rectangle.md).

### Scale

- Pop up
    - Pop up width and height
        ```javascript
        sizer.popUp(duration);
        // sizer.popUp(duration, undefined, ease);
        ```
        - `ease` : [Ease function](tween.md/#ease-equations), default is `'Cubic'`.
    - Pop up width only
        ```javascript
        sizer.popUp(duration, 'x');
        // sizer.popUp(duration, 'x', ease);
        ```
    - Pop up height only
        ```javascript
        sizer.popUp(duration, 'y');
        // sizer.popUp(duration, 'y', ease);
        ```
    - Pop up via config
        ```javascript
        sizer.popUp({
            duration: undefined,
            orientation: undefined,
            ease: undefined,
        })
        ```
        - `orientation` : `undefined`, `x`, or `y`
- Scale down destroy
    - Scale down width and height
        ```javascript
        sizer.scaleDownDestroy(duration);
        // sizer.scaleDownDestroy(duration, undefined, ease);
        ```
        - `ease` : [Ease function](tween.md/#ease-equations), default is `'Linear'`.
    - Scale down width only
        ```javascript
        sizer.scaleDownDestroy(duration, 'x');
        // sizer.scaleDownDestroy(duration, 'x', ease);
        ```
    - Scale down height only
        ```javascript
        sizer.scaleDownDestroy(duration, 'y');
        // sizer.scaleDownDestroy(duration, 'y', ease);
        ```
- Scale down without destroy
    - Scale down width and height
        ```javascript
        sizer.scaleDownDestroy(duration, undefined, ease, false);
        ```
    - Scale down width only
        ```javascript
        sizer.scaleDownDestroy(duration, 'x', ease, false);
        ```
    - Scale down height only
        ```javascript
        sizer.scaleDownDestroy(duration, 'y', ease, false);
        ```

### Fade

- Fade in
    ```javascript
    sizer.fadeIn(duration);
    ```
- Fade out destroy
    ```javascript
    sizer.fadeOutDestroy(duration);
    ```
- Fade out without destroy
    ```javascript
    sizer.fadeOutDestroy(duration, false);
    ```

### Drag top-most sizer

- Draggable
    ```javascript
    sizer.setDraggable();
    // sizer.setDraggable(true);
    ```
- Disable
    ```javascript
    sizer.setDraggable(false);
    ```

### Pin game object

```javascript
sizer.pin(gameObject);
```

!!! note
    Method `sizer.add` is override in each sizer class usually.

### Draw bounds

Draw all bounds of children.

```javascript
sizer.drawBounds(graphics, color);
```

- `graphics` : [Graphics game object](graphics.md)
- `color` : Default value is `0xffffff`

### Other properties

This game object inherits from [ContainerLite](containerlite.md).