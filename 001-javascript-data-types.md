### JavaScript Data Types
There are eight basic data types in JavaScript. They are:

| Data Types | Description | Example |
| --- | ---- | -------- |
| String | represents textual data | 'hello', "hello world!", etc |
| Number | an integer or a floating-point number | 3, 3.234, 3e-2, etc |
| BigInt | an integer with arbitrary precision | 900719925124740999n, 1n, etc |
| Boolean | Any of two values: true or false | true and false |
| undefined | a data type whose variable is not initialized | let a; |
| null | denotes a null value | let a = null; |
| Symbol | data type whose instances are unique and immutable | let value = Symbol('hello');|
| Object | key-value pairs of collection of data | let student = { }; |

1.  **JavaScript String**
String is used to store text. In JavaScript, strings are surrounded by quotes:

Single quotes: 'Hello'
Double quotes: "Hello"
Backticks: `Hello`

For example,

```node
//strings example
const name = 'ram';
const name1 = "hari";
const result = `The names are ${name} and ${name1}`;
```

2.  **JavaScript Number**

Number represents integer and floating numbers (decimals and exponentials). For example,

```node
const number1 = 3;
const number2 = 3.433;
const number3 = 3e5 // 3 * 10^5
```

3.  **JavaScript BigInt**


```node
// BigInt value
const value1 = 900719925124740998n;

// Adding two big integers
const result1 = value1 + 1n;
console.log(result1); // "900719925124740999n"

const value2 = 900719925124740998n;

// Error! BitInt and number cannot be added
const result2 = value2 + 1; 
console.log(result2); 
```

**Output**

```node
900719925124740999n
Uncaught TypeError: Cannot mix BigInt and other types
```

4.  **JavaScript Boolean**

This data type represents logical entities. Boolean represents one of two values: true or false. It is easier to think of it as a yes/no switch. For example,

```node
const dataChecked = true;
const valueCounted = false;
```

5.  **JavaScript undefined**
The undefined data type represents value that is not assigned. If a variable is declared but the value is not assigned, then the value of that variable will be undefined. For example,


```node
let name;
console.log(name); // undefined
```

6.  **JavaScript null**
In JavaScript, null is a special value that represents empty or unknown value. For example,

```node
const number = null;
```

7.  **JavaScript Symbol**
A value having the data type Symbol can be referred to as a symbol value. Symbol is an immutable primitive value that is unique. For example,
```node
// two symbols with the same description
const value1 = Symbol('hello');
const value2 = Symbol('hello');
```

8.  **JavaScript Object**
An object is a complex data type that allows us to store collections of data. For example,

```node
const student = {
    firstName: 'ram',
    lastName: null,
    class: 10
};
```













