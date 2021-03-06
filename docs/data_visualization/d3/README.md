# D3

> Data driven document is an open source Javascript library utilizes SVG, HTML, CSS to create custom interactive visualizations with data.

## Selectors

<!-- tabs:start -->

<!-- tab:.select() -->

Returns the first matching element in the HTML document

<!-- tab:.selectAll() -->

Returns the all the matching elements in the HTML document

<!-- tabs:end -->

## Methods

The following methods can be used after after selecting elements using d3.select() or d3.selectAll()

| Method                      | Description                                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------------- |
| .text('content')            | Gets or sets the text of the selected element                                               |
| .style('property', 'value') | Gets or sets the style of the selected element                                              |
| .append('element name')     | Adds an element inside the selected element but just before the end of the selected element |
| .insert('element name')     | Inserts a new element in the selected element                                               |
| .remove()                   | Removes the specified element from the DOM                                                  |
| .html('content')            | Gets or sets the inner HTML of selected element                                             |
| .attr('name','value')       | Gets or sets an attribute on the selected element                                           |
| .property('name', 'value')  | Gets or sets an attribute on the selected element                                           |
| .classed('css class', bool) | Gets, adds or removes a css class from the selection                                        |

## Function of Data

Each of the methods can take in a constant value or a function

```html
<p>Error: This is error.</p>
<p>Warning:This is warning.</p>

<script>
  d3.selectAll("p").style("color", function (d, i) {
    var text = this.innerText;

    if (text.indexOf("Error") >= 0) {
      return "red";
    } else if (text.indexOf("Warning") >= 0) {
      return "yellow";
    }
  });
</script>
```

## Event handling

D3 supports built-in events and custom events

| Event Methods        | Description                                                                                                      |
| -------------------- | ---------------------------------------------------------------------------------------------------------------- |
| selection.on()       | Add or remove event listeners to capture event types like click, mouseover, mouseout etc.                        |
| selection.dispatch() | Captures event types like click, mouseover, mouseout. Typenames is the eventname, listener is the event listener |
| d3.event             | Event object to access standard event fields such as timestamp or methods like preventDefault                    |
| d3.mouse(container)  | Gets the x and y coordinates of the current mouse position in the specified DOM element.                         |
| d3.touch()           | Gets the touch coordinates to a container                                                                        |

Example

```html
<div></div>
<script>
  d3.selectAll("div")
    .on("mouseover", function () {
      d3.select(this).style("background-color", "orange");

      // Get current event info
      console.log(d3.event);

      // Get x & y co-ordinates
      console.log(d3.mouse(this));
    })
    .on("mouseout", function () {
      d3.select(this).style("background-color", "steelblue");
    });
</script>
```

## Animation

D3 simplifies the process of animations with transitions. Transitions are made on DOM selections using \<selection\>.transition() method.

| Method                 | Description                                                                |
| ---------------------- | -------------------------------------------------------------------------- |
| selection.transition() | this schedules a transition for the selected elements                      |
| transition.duration()  | duration specifies the animation duration in milliseconds for each element |
| transition.ease()      | ease specifies the easing function, example: linear, elastic, bounce       |
| transition.delay()     | delay specifies the delay in animation in milliseconds for each element    |

## Data Binding

| Method   | Description                                                                               |
| -------- | ----------------------------------------------------------------------------------------- |
| .data()  | Joins data to the selected elements                                                       |
| .enter() | Creates a selection with placeholder references for missing elements                      |
| .exit()  | Removes nodes and adds them to the exit selection which can be later removed from the DOM |
| .datum() | Injects data to the selected element without computing a join.                            |

## Data Loading

| Method    | Description                                                                                                                       |
| --------- | --------------------------------------------------------------------------------------------------------------------------------- |
| d3.csv()  | Sends http request to the specified url to load .csv file or data and executes callback function with parsed csv data objects.    |
| d3.json() | Sends http request to the specified url to load .json file or data and executes callback function with parsed json data objects.  |
| d3.tsv()  | Sends http request to the specified url to load a .tsv file or data and executes callback function with parsed tsv data objects.  |
| d3.xml()  | Sends http request to the specified url to load an .xml file or data and executes callback function with parsed xml data objects. |

## Scales

```js
var data = [100, 400, 300, 900, 850, 1000];

var width = 500,
  barHeight = 20,
  margin = 1;

var scale = d3
  .scaleLinear()
  .domain([d3.min(data), d3.max(data)])
  .range([50, 500]);

var svg = d3
  .select("body")
  .append("svg")
  .attr("width", width)
  .attr("height", barHeight * data.length);

var g = svg
  .selectAll("g")
  .data(data)
  .enter()
  .append("g")
  .attr("transform", function (d, i) {
    return "translate(0," + i * barHeight + ")";
  });

g.append("rect")
  .attr("width", function (d) {
    return scale(d);
  })
  .attr("height", barHeight - margin);

g.append("text")
  .attr("x", function (d) {
    return scale(d);
  })
  .attr("y", barHeight / 2)
  .attr("dy", ".35em")
  .text(function (d) {
    return d;
  });
```

![Image](_media/scales.png)

## Axes

```js
var width = 400,
  height = 100;

var data = [10, 15, 20, 25, 30];
var svg = d3
  .select("body")
  .append("svg")
  .attr("width", width)
  .attr("height", height);

var xscale = d3
  .scaleLinear()
  .domain([0, d3.max(data)])
  .range([0, width - 100]);

var yscale = d3
  .scaleLinear()
  .domain([0, d3.max(data)])
  .range([height / 2, 0]);

var x_axis = d3.axisBottom().scale(xscale);

var y_axis = d3.axisLeft().scale(yscale);

svg.append("g").attr("transform", "translate(50, 10)").call(y_axis);

var xAxisTranslate = height / 2 + 10;

svg
  .append("g")
  .attr("transform", "translate(50, " + xAxisTranslate + ")")
  .call(x_axis);
```

![Axes](_media/axes.png)

## Resources

More resources found on [Tutorialsteacher.com](https://www.tutorialsteacher.com/d3js/d3js-resources)
