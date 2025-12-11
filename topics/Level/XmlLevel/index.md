# XML level file
Table of contents:
- [Settings layer](#settings-layer)
- [Objects layer](#objects-layer)
    - [Additional information for objects](#additional-information-for-objects)
        - [`target`](#target)
    - [Global attributes](#global-attributes)
        - [Position attributes](#position-attributes)

An **XML level** is a level that uses the XML markup language to store level settings & objects.

You can learn XML at [Learn X in Y Minutes](https://learnxinyminutes.com/xml/).

Here's what an XML level file should look like:
```xml
<map>
    <layer name="settings">
        <map width="320" height="480" gridSize="20" />
        <gameDesign twoParts="false" ropePhysicsSpeed="1" nightLevel="false" />
    </layer>
    <layer name="Objects">
        <!-- Objects are placed here -->
    </layer>
</map>
```
> [!TIP]
> Internally, the game calls a level as a "map". In this website, we will call them as "levels" from now on.

In an XML level, there's a `map` element, which inside has `layer` elements which will be documented below.

## Settings layer
The `layer` element with the `name` attribute set to "settings" has options for the level.

## Objects layer
The `layer` element with the `name` attribute set to "Objects" has objects for the level.

List of objects:

| XML Tag         | Description         | First version |
| --------------- | ------------------- | ------------- |
| `target`        | Om Nom.             | 1.0           |
| `candy`         | The candy.          | 1.0           |
| `star`          | A yellow star.      | 1.0           |
| `hiddenElement` | A blue star.        | ???           |

### Global attributes
These are attributes to objects that are not specific to any object.

#### Position attributes
The `x` and `y` attributes specify the X and Y coordinates of the object. Any amount higher than the level's `width` and `height` will be off-screen.

Examples:
```xml
<target x='161' y='433' />
<candy x='20' y='256' />
```

### Additional information for objects
#### `target`
In Cut the Rope Time Travel, there's a `targetType` attribute, which has 2 possible values:
- `basic`: Normal Om Nom
- `special`: Special variant of Om Nom for the specific box
