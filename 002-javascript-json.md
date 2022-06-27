### JS JSON


**JSON.parse()**
A common use of JSON is to exchange data to/from a web server.

When receiving data from a web server, the data is always a string.

Parse the data with JSON.parse(), and the data becomes a JavaScript object.

For example,
Imagine we received this text from a web server:
```node
'{"name":"Bipon", "age":30, "city":"Khulna"}'
```

Use the JavaScript function **JSON.parse()** to convert text into a JavaScript object:

```node
const obj = JSON.parse('{"name":"Bipon", "age":30, "city":"Khulna"}');
```

Use the JavaScript object in your page:

```node
<!DOCTYPE html>
<html>
<body>

<h2>Creating an Object from a JSON String</h2>

<p id="demo"></p>

<script>
const txt = '{"name":"Bipon", "age":30, "city":"Khulna"}'
const obj = JSON.parse(txt);
document.getElementById("demo").innerHTML = obj.name + ", " + obj.age;
</script>

</body>
</html>
```

**Array as JSON**

When using the JSON.parse() on a JSON derived from an array, the method will return a JavaScript array, instead of a JavaScript object.


```node
<!DOCTYPE html>
<html>
<body>

<h2>Parsing a JSON Array.</h2>
<p>Data written as an JSON array will be parsed into a JavaScript array.</p>
<p id="demo"></p>

<script>
const text = '[ "Ford", "BMW", "Audi", "Fiat" ]';
const myArr = JSON.parse(text);
document.getElementById("demo").innerHTML = myArr[0];
</script>

</body>
</html>
```









