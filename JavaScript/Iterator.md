```javascript
const text = "Rhyme";
const it = text[Symbol.iterator]();
console.log(it.next())

// console: { value: 'R', done: false }

const cities = ["Sofia", "New Delhi", "Tokyo"];
const city = cities[Symbol.iterator]();
let result  = city.next();

while (!result.done) {
    console.log(result.value)
    result = city.next();
}

// console: Sofia
//          New Delhi
//          Tokyo
```
