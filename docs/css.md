# CSS

## Different Ways To Set Colors

```CSS
element {
  color: Yellow; /*Keyword */
  color: #8FBC8F; /* Hex Code */
  color: rgb(23, 45, 23); /* RGB*/
  color: hsla(34, 100%, 50%, 0.1); /* HSLA*/
}
```

### Responsive Images

```HTML
  <picture>
    <source srcset="img/peace-pie-original.jpg" media="(min-width: 1200px)"/>
    <source srcset="img/peace-pie-500.jpg" media="(min-width: 800px)"/>
    <img src="img/peace-pie-original.jpg" alt="The original peace pie"/>
  </picture>
```

#### Polyfill

```HTML
  <head>
    <script>
      document.createElement("picture")
    </script>
    <script src="picturefill.min.js"></script>
  </head>
```
