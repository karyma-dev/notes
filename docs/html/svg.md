# SVG

Scalable Vector Graphics is an text-based image that sits in the DOM.

```html
<svg width="500" height="500">
  <rect x="0" y="0" width="200" height="200"></rect>
  <line x1="100" y1="50" x2="500" y2="50" stroke="black" />
  <circle cx="250" cy="50" r="50" />
  <ellipse cx="250" cy="25" rx="100" ry="25" />
  <text x="250" y="25">Your text here</text>
</svg>
```

## Attributes

| Style Attribute | Description                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------ |
| Fill            | This is the fill color for your element. It can be color name, hex value, or RGB or RGBA values.             |
| stroke          | This is the stroke color. Like our line example above, we can specify a color for our element.               |
| stroke-width    | Stroke width specifies the width of our line or boundary. This is in pixels.                                 |
| opacity         | Opacity will specify an opacity/transparency number. 0 is completely transparent and 1 is completely opaque. |
| font-family     | For text elements, we can specify the font-family. This works like CSS.                                      |
| font-size       | We can also specify the font-size for text elements.                                                         |

## Example

```html
<style>
  svg rect {
    fill: orange;
  }

  svg text {
    fill: white;
    font: 10px sans-serif;
    text-anchor: end;
  }
</style>
<svg class="chart" width="420" height="120">
  <g transform="translate(0,0)">
    <rect width="50" height="19"></rect>
    <text x="47" y="9.5" dy=".35em">5</text>
  </g>
  <g transform="translate(0,20)">
    <rect width="100" height="19"></rect>
    <text x="97" y="9.5" dy=".35em">10</text>
  </g>
  <g transform="translate(0,40)">
    <rect width="120" height="19"></rect>
    <text x="117" y="9.5" dy=".35em">12</text>
  </g>
</svg>
```
