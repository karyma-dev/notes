# Methods

## .text()

Add or modify content of selected element

```html
<div>
  <p></p>
  <p>Second Paragraph</p>
</div>

<script>
  d3.select("p").text("First Paragraph.");
</script>
```

## .append()

Create and add new DOM element at the end of selected element

```html
<div>
  <p>First paragraph</p>
</div>

<script>
  d3.select("p").append("p").text("Second Paragraph");
</script>
```

## .insert()

Create and insert new DOM element before the selected element closing tag

```html
<div>
  <p>First paragraph.</p>
</div>

<script>
  d3.select("div").insert("p").text("Second paragraph.");
</script>
```

## .remove()

Removes or deletes the selected DOM element

```html
<p>First paragraph</p>
<p>Second paragraph</p>

<script>
  d3.select("p").remove();
</script>
```

## .html()

Sets the inner html of selected element

```html
<p>First paragraph</p>

<script>
  d3.select("p").html("<p>This is the new First Paragraph</p>");
</script>
```

## .attr()

Sets the attribute and value of the selected element

```html
<body>
  <p>First Paragraph</p>
  <script>
    d3.select("p").attr("class", "error");
  </script>
</body>
```

## .property()

Used for certain properties that you cannot access with .attr() method. Sets the property and value of selected element

```html
<p>D3</label><input type="checkbox" />
<p>jQuery</label><input type="checkbox" />

<script>
    d3.select("input").property("checked",true);
</script>
```

## .style()

```html
<p>First Paragraph</p>

<script>
  d3.select("p").style("color", "red");
</script>
```

## .classed()

Used to add or remove classes on selected element

```html
<style>
  .error {
    color: red;
  }
</style>
<body>
  <p>This is error.</p>

  <script>
    d3.select("p").classed("error", true);
  </script>
</body>
```
