# JavaScript required to know React

- JSX compiles to simple javascript.
- Template literals are regular strings with super power.
- Arrow function is same as regular funtions with minor differences like
    - Implicit Returns
    - 
- One thing to note in arrow function is opening and closing parantheses i.e ( ). In this way, we are performing implicit return capabilities when working with JSX.
- Parameter defaults is one way to define/declare default values for given parameter for your functions. In JavaScript, function parameters default to undefined


### Template Literals
```js
var firstName = 'Parvez'
var lastName = 'Shaikh'

console.log(`${firstName} ${lastName}!`);

// Which is also same as
console.log(firstName +' '+ lastName);

// In React, how can we use this
function Box({ className, ...props }) {
    return (
        <div className={`box ${className}`} {...props}/>
    )
}
```

### ShortHand Property Names (New Notations in ECMAScript 2015)
```js
let a = 'hello'
let b = 42
let c = {d: [true, false]}
console.log({ a, b, c })

// this is same as
console.log({ a: a, b: b, c: c })
```

### Arrow Functions
```js
const getFive = () => 5
const addFive = (a) => a + 5
const divide = (a, b) => a / b

// All this is same as
function getFive() {
    return 5
}

function addFive(a) {
    return a + 5
}

function divide(a, b) {
    return a / b
}

// In React, we can use arrow function here
function TeddyBearList({ teddyBearList }) {
    return (
        <ul>
            {teddyBearList.map(teddyBear => (
                <li key={teddyBear.id}>{teddyBear.name}</li>
            ))}
        </ul>
    )
}
```

### Destructuring
```js
const obj = {x: 3.5, y: 7.8}

function makeCalculation({ x, y: d, z = 4 }) {
    return Math.floor((x + d + z) / 3)
}

// Above is same as
function makeCalculation(obj) {
    const { x, y:d, z = 4 } = obj
    return Math.floor((x + d + z) / 3)
}

// Which is same as
function makeCalculation(obj) {
    const x = obj.x
    const d = obj.y
    const z = obj.z === undefined ? 4 : obj.z
    return Math.floor((x + d + z) / 3)
}

// In React
function UserGitHubImg({username='ghost', ...props}) {
    return <img src={`https://github.com/${username}.png`} {...props}/>
}

// Exercise:
function nestedArrayAndObject() {
  // refactor this to a single line of destructuring...
  const info = {
    title: 'Once Upon a Time',
    protagonist: {
      name: 'Emma Swan',
      enemies: [
        {name: 'Regina Mills', title: 'Evil Queen'},
        {name: 'Cora Mills', title: 'Queen of Hearts'},
        {name: 'Peter Pan', title: `The boy who wouldn't grow up`},
        {name: 'Zelena', title: 'The Wicked Witch'},
      ],
    },
  }
  // replace the next few `const` lines with this
  const {title, protagonist: { name: protagonistName, enemies }} = info 
  const { title: enemyTitle, name:  enemyName } = enemies[3]
  const infoTitle = info.title
  return `${enemyName} (${enemyTitle}) is an enemy to ${protagonistName} in "${infoTitle}"`
}

```

### Parameter Defaults

```js
function add(a, b = 0) {
    return a + b
}

// The above is same as
const add(a, b = 0) => a + b

// is same as
function add(a, b) {
    b = b === undefined ? 4 : b
    return a + b
}
```