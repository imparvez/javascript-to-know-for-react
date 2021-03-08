# How Javascript works?

- Javascript is an interpreted language.
- In Javascript, there is no compilation step, instead an interpreter in the browser reads over the Javascript code and interpret each line, runs it.
- In browser, we have Javascript engine that takes the code and executes it. The parser will know rules for JS to ensures it.
- Javascript engine is a program or an interpreter which executes Javascript code. A Javascript engine can be implemented as an standard interpreter, or just-in-time compiler that compiles Javascript to bytecode in some form.
- JavaScript is single-threaded or that it uses a callback queue.
- Javascript can do ONE THING AT A TIME.

### Javascript Google's V8 Engine:
- It is used inside Google Chrome and in NodeJS
- The engine consist of two main components
    - Memory Heap = This is where memory allocation happens
    - Call Stack = This is where you stack frames are as your code executes
- There are numbers of APIs in the browser which is used by developers for eg: setTimeout, however those APIs are not provided by JavaScript engine. They are Web APIs which are provided by browsers like the DOM, AJAX, setTimeout and many more.

### Callstack
- It is basically a data structure which records basically where in the program we are.
- If we step into the function, we put it on top of the stack.
- If we return from a function, we pop off the top of the stack.
- Each entry in the call stack is called STACK FRAME(Refer CallStack Demo).

```js
function multiply(x, y) {
    return x * y
}

function printSquare(x) {
    var s = multiply(x, x)
    console.log(s)
}

printSquare(2)
```
When the Engine starts executing this code, at first the call stack is empty.
![CallStack Demo](https://miro.medium.com/max/1400/1*Yp1KOt_UJ47HChmS9y7KXw.png)

Reference:
[Part 1](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf)
[Part 2](https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e)