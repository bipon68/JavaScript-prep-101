### JavaScript CallStack
JavaScript CallStack


**JavaScript CallStack ?**

An understanding of the call stack will give clarity to how “function hierarchy and execution order” works in the JavaScript engine.
The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.

```node 
function ceo(){
            console.log("Let's make a dent in the univers");
            cto()
        }
        function cto(){
            console.log("Let's make a gamechange product")
            vpeng()
        }
        function vpeng(){
            console.log("Let's make a Javascript framework")
            techlead()
        }
        function techlead(){
            console.log("Let's make a port angular typescript")
            developer()
        }
        function developer(){
            console.log("Let's copy some code from Stackoverflow")
            throw new Error("The code did'n work")
        }
        ceo();
```

**Output**

```node
Let's make a dent in the univers
Let's make a gamechange product
Let's make a Javascript framework
Let's make a port angular typescript
Let's copy some code from Stackoverflow
Uncaught Error: The code did'n work
```

At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

**A nested function that prints a stack trace error to the console**

```node 
function firstFunction(){
  throw new Error('Stack Trace Error');
}

function secondFunction(){
  firstFunction();
}

function thirdFunction(){
  secondFunction();
}

thirdFunction();
```

**Output**

```node
Uncaught Error: Stack Trace Error
```

**A function that calls another function to show how the stack handles multiple function calls**

```node 
function firstFunction(){
  console.log("Hello from firstFunction");
}

function secondFunction(){
  firstFunction();
  console.log("The end from secondFunction");
}

secondFunction();
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

[Call Stack](https://github.com/priya42bagde/33-js-concepts#1-call-stack),
[JavaScript Call Stack](https://www.javascripttutorial.net/javascript-call-stack/)
