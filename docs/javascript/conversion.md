# Conversion

### Number Conversion

```js
Number('3.14'); // returns 3.14
Number(' '); // returns 0
Number(''); // returns 0
Number('99 88'); // returns NaN
parseInt();
parseFloat();
let x = +y; // Unary + operator, converts variable to number, if variable cannot be converted then it becomes number with the value of NaN

let d = new Date();
Number(d); // Convert dates to number
d.getTime();
```

### String Conversion

```js
String(x);
String(123);
String(100 + 23);
String(false);
x.toString(); // Number method
x.toExponential();
x.toFixed();
x.toPrecision();

let d = new Date();
String(d);
d.toString();
```
