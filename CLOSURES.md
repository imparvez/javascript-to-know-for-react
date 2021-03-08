# What is Closure?

- You have a closure when a function accesses variable defined outside of it.
- Function can access outside variables.
- Wrapping code in a function and calling it once doesn’t change the result.
- Any variable inside a function is a local variable of that function.

```js
let users = ['Alice', 'Dan', 'Jessica']
let query = 'A'
let user = users.filter(user => user.startsWith(query))
```

`user => user.startsWith(query)` this is a function which uses query variable defined outside this function.
That's a closure.

```js
function liveADay() {
  let food = 'cheese'; // Declare `food`
  function eat() {
    console.log(food + ' is good'); // Read `food`
  }
  eat();
}
liveADay();
```

- First, we declare the liveADay function at the top level. 
- We immediately call it. It has a food local variable. 
- It also contains an eat function. 
- Then it calls that eat function. 
- Because eat is inside of liveADay, it “sees” all of its variables. 
- This is why it can read the food variable.
- We say that there is a closure when a function (such as eat) reads or writes a variable (such as food) that is declared outside of it (such as in liveADay).
