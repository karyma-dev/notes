# Animation

## .transition()

Indicates the start of a transition which allows application of other transition functions

```html
<div id="container"></div>

<script>
  d3.select("#container")
    .transition()
    .duration(1000)
    .style("background-color", "red");
</script>
```

## .ease()

Controls the motion of the transition. [Examples](https://bl.ocks.org/d3noob/1ea51d03775b9650e8dfd03474e202fe)

## .delay()

Sets the delay for selected element

```js
bar1.transition().ease(d3.easeLinear).duration(2000).attr("height", 100);

bar2
  .transition()
  .ease(d3.easeLinear)
  .duration(2000)
  .delay(2000)
  .attr("height", 100);
```
