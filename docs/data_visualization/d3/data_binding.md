# Data Binding

## .data()

Joins the specified array of data to the selected DOM elements and return the updated selection.

```js
var myData = ["Hello World!"];

var p = d3
  .select("body")
  .selectAll("p")
  .data(myData)
  .text(function (d) {
    return d;
  });
```

## .enter()

Dynamically creates placeholder references corresponding to the number of data values.

```js
var data = [4, 1, 6, 2, 8, 9];
var body = d3
  .select("body")
  .selectAll("span")
  .data(data)
  .enter()
  .append("span")
  .text(function (d) {
    return d + " ";
  });
```

## .exit()

Dynamically removes DOM elements

```html
<p>D3 Tutorials</p>
<p></p>
<p></p>
<script>
  var myData = ["Hello World!"];

  var p = d3
    .select("body")
    .selectAll("p")
    .data(myData)
    .text(function (d, i) {
      return d;
    })
    .exit()
    .remove();
</script>
```

## .datum()

Binds directly to an element used for static visualization which does not need updates

```html
<p></p>
<script>
  d3.select("body")
    .select("p")
    .datum(100)
    .text(function (d, i) {
      return d;
    });
</script>
```
