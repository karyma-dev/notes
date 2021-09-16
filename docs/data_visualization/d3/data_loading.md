# Data Loading

## d3.csv(url, callback)

Used to load csv file or csv data

```csv
Name, Age
John, 30
Jane, 32
```

```js
d3.csv("/data/employees.csv", function (data) {
  for (var i = 0; i < data.length; i++) {
    console.log(data[i].Name);
    console.log(data[i].Age);
  }
});

// Same as .csv
d3.csv("/data/employees.csv").get(function (data) {
  console.log(data);
});

// Same as .csv
d3.request("/data/employees.csv")
  .mimeType("text/csv")
  .response(function (xhr) {
    return d3.csvParse(xhr.responseText);
  })
  .get(function (data) {
    console.log(data);
  });

d3.csv("/data/employees.csv")
  .row(function (d) {
    return {
      age: d.age,
      name: d.name.toUpperCase(), // converting name to upper case
    };
  })
  .get(function (data) {
    console.log(data);
  });
```

## d3.json(url, callback)

Returns an array of objects from JSON file

```json
[{
    "name": "John",
    "age": 30,
    "city": "New York"
},
{
    "name": "Jane",
    "age": 20,
    "city": "San Francisco"
}];
```

```js
d3.json("/data/users.json", function (data) {
  console.log(data);
});
```

## d3.tsv(url, callback)

Returns an array of objects from tsv file

```tsv
Name    Age
John    30
Jane    32
```

```js
d3.tsv("/data/employees.tsv", function (data) {
  for (var i = 0; i < data.length; i++) {
    console.log(data[i].Name);
    console.log(data[i].Age);
  }
});
```

## d3.xml(url, callback)

Returns an array of objects from xml file

```xml
<?xml version="1.0" encoding="UTF-8"?>
<root>
<row>
    <Name>John</Name>
    <Age>30</Age>
</row>
<row>
    <Name>Jane</Name>
    <Age>32</Age>
</row>
</root>
```

```js
d3.xml("/data/employees.xml", function (data) {
  console.log(data);
});
```

### Example

```json
[
  {
    "name": "Jon",
    "age": 30,
    "location": "The Wall"
  },
  {
    "name": "Arya",
    "age": 12,
    "location": "Braavos"
  },
  {
    "name": "Cersei",
    "age": 42,
    "location": "Kings Landing"
  },
  {
    "name": "Tyrion",
    "age": 40,
    "location": "Kings Landing "
  }
]
```

```js
d3.json("/data/users.json", function (error, data) {
  d3.select("body")
    .selectAll("p")
    .data(data)
    .enter()
    .append("p")
    .text(function (d) {
      return d.name + ", " + d.location;
    });
});
```
