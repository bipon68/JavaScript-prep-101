### JavaScript Scope
JavaScript Scope


**JavaScript Scope ?**

Need to know where you can access or use your declared variables/functions. If you want to make a variable or function private or if you want to access a variable from everywhere, how or where to declare it.

There are mainly two types of scoping in JavaScript:

1. Local scope

2. Global scope

The main topics discussed in scoping are:

- Where can you access your variable or function?
- Each new function creates a scope
- Parent-child relationship in lexical scoping
- A variable declared in one function cannot be passed to another function, i.e. cannot be accessed.

```node
function localScope() {
   var local = 'I am local to my own function';
   console.log(local);
}
```

Calling it will show the correct output:

```node
localScope();
```

![dd](./images/local-scope.png)

But now if we want to access this **local** variable **localScope()** somewhere outside this or any other function, then it cannot be accessed and in this case we will get real error.

```node 
function localScope() {
   var local = 'I am local to my own function';
   console.log(local);
}

localScope();

console.log(local);
```

![dd](./images/local-scope-error.png)

```
aPromise(true);
```

**Global (Global) Scope**

If the variable is not declared inside a function, then it is a variable declared in the global scope, that means the variable declared anywhere outside the function will get the global scope. They are also called global variables. Global variables can be accessed from within any function or from anywhere

```node
var globalVar = 'I am a Global Variable';

function globalScope() {
   console.log('Inside a Function: ' + globalVar);
}

globalScope();

console.log('Outside: ' + globalVar);
```

![dd](./images/global-variable.png)

Now this idea of ​​scoping applies to variables as well as to functions and objects.

This means that if you declare a function in global scope, you can access it from anywhere globally. All the functions used in the above examples are declared in global scope.

```node
function globalFunc() {
   console.log('Global Function');
}
```

Now calling this function will work fine:

```node
globalFunc();
```

![dd](./images/global-function.png)

Similarly if you declare another function inside a function then the function declared inside the function gets the local scope of that function. And this function can only be called inside that function. Can't call outside as it has no scope.


```node 
function anoGlobalFunc() {
   console.log('Global Function');
   function localFunc() {
      console.log('Local Function');
   }
   localFunc();
}
```
Note that I called the local function **localFunc()** inside that function, because that's where it's scope is. Now calling the global function **anoGlobalFunc()** will execute both.


```node
anoGlobalFunc();
```
![dd](./images/global-and-local-function.png)

 **localFunc()** But now if I call this local function  **anoGlobalFunc()** outside it will show error:


```
localFunc();
```
![dd](./images/local-function-error.png)


Same goes for the same object. When declared inside a function, it gets the local scope of that function. Cannot be accessed anywhere except inside the function itself. And if declared outside global scope it will get global scope and can be accessed from everywhere.

```node 
var person = {
   name: 'Bipon Biswas',
   age: 25
}
```

Now this object can be accessed from everywhere:

```node
console.log(person);
```

![dd](./images/scope-example-object.png)


But if this object is declared inside a function, then that object gets local scope of that function and can be accessed only from inside that function.

```node
function objectFunc() {
   var localObj = {
      name: 'Bipon Biswas',
      age: 25
   }
   console.log(localObj);
}
```
Now calling this function will show everything fine:

```node
objectFunc();
```
![dd](./images/scope-object-function.png)

```node
console.log(localObj);
```
![dd](./images/scope-object-function-error.png)

**Lexical Scoping (Lexical Scoping)**

In lexical scoping, a relation of a parent function with a child function is created. Now what does parent-child function mean? Yes, if we declare another function inside a function, then the function inside which we declared the new function is the parent function. And any other function declared inside the parent function is a child function of that parent function. Hope the following example will clear the idea:

```node
function parentFunction() {
   //some codes here
   function childFunction() {
      //some more codes
   } 
}
```
Now here is the **parentFunction()** global function and **childFunction()** **parentFunction()**  its local function. Now we know that variables, functions or objects declared inside a function get local scope and can be accessed only inside that function. But because of lexical scoping, **parentFunction()** anything local declared inside here can be accessed from **parentFunction()** within it, and all of its child functions **childFunction()** can also be accessed from inside here.

```node
function parentFunction() {
   var a = 9;
   function childFunction() {
      var b = 11;
      console.log('Sum: ' + (a + b));
   } 
   childFunction();
}
```
Now **parentFunction()** calling K will show the result exactly as it should:

```node
parentFunction();
```

![dd](./images/lexical-scope.png)

**Another example**

``` node
function parentFunction(){
    var a = 9;
    function childFunction(){
        var b = 11;
        // console.log('Sum : ' + (a+b))
        function childFunctionC(){
            var c = 10
            console.log('Sum3 : ' + (a + b + c))
        }
        childFunctionC()
    }
    childFunction();
    
}
parentFunction()
```

**Output**

``` node
Sum3 : 30
```


**Reference**

[JavaScript Promises In 10 Minutes](https://www.youtube.com/watch?v=DHvZLI7Db8E)
