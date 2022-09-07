### JavaScript Primitives
JavaScript Primitives


**JavaScript Primitives ?**

In JavaScript there are 6 primitive types: undefined, null, boolean, string and number, Symbols (new in ECMAScript 2015). Everything else is an object. The primitive types boolean, string and number can be wrapped by their object counterparts. These objects are instances of the Boolean, String and Number constructors respectively.

```node 
typeof true; //"boolean"
typeof Boolean(true); //"boolean"
typeof new Boolean(true); //"object"
typeof (new Boolean(true)).valueOf(); //"boolean"
 
typeof "abc"; //"string"
typeof String("abc"); //"string"
typeof new String("abc"); //"object"
typeof (new String("abc")).valueOf(); //"string"
 
typeof 123; //"number"
typeof Number(123); //"number"
typeof new Number(123); //"object"
typeof (new Number(123)).valueOf(); //"number"
```

**Primitive types**

Primitive types have no methods attached to them; so you'll never see undefined.toString(). Also because of this, primitive types are immutable, because they have no methods attached that can mutate it.

You can reassign a primitive type to a variable, but it will be a new value, the old one is not, and cannot, be mutated.

```node
const answer = 42
answer.foo = "bar";
answer.foo; // undefined
```

Primitive types are immutable

**Primitive types are stored by value, objects are stored by reference**

```node 
"dog" === "dog"; // true
14 === 14; // true

{} === {}; // false
[] === []; // false
(function () {}) === (function () {}); // false
```
Furthermore, the primitive types are stored as the value themselves, unlike objects, which are stored as a reference. This has implications when performing equality checks.

**Wrapper Objects**

The confusion arises because of functions like **String**, **Number**, **Boolean**, **Function** etc. which, when called with **new**, creates wrapper objects for these primitive types.

**String** is a global function that creates a primitive string when passed in an argument; it will try to convert that argument into a string.

```node
String(1337); // "1337"
String(true); // "true"
String(null); // "null"
String(undefined); // "undefined"
String(); // ""
String("dog") === "dog" // true
typeof String("dog"); // "string"
```
But you can also use the String function as a constructor function.

```node
const pet = new String("dog")
typeof pet; // "object"
pet === "dog"; // false
```

And this will create a new object (often referred to as wrapper object) representing the string "dog", with the following properties:

```node 
{
  0: "d",
  1: "o",
  2: "g",
  length: 3
}
```

**Output**

```node
Hello from firstFunction
The end from secondFunction
```

This is what happens when the code is run:

1. When **secondFunction()** gets executed, an empty stack frame is created. It is the main (anonymous) entry point of the program.
2. **secondFunction()** then calls **firstFunction()** which is pushed into the stack.
3. **firstFunction()** returns and prints “Hello from firstFunction” to the console.
4. **firstFunction()** is pop off the stack.
5. The execution order then move to **secondFunction()**.
6. **secondFunction()** returns and print “The end from secondFunction” to the console.
7. **secondFunction()** is pop off the stack, clearing the memory.

**A recursive function that will throw a maxiumu call stack error.**

```node 
function callMyself(){
  callMyself();
}

callMyself();
```

**Output**

```node
Uncaught RangeError: Maximum call stack size exceeded
```

**In summary**

The key takeaways from the call stack are:

1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.

**Reference**

[Call Stack](https://github.com/priya42bagde/33-js-concepts#1-call-stack)
