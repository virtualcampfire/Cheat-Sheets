```javascript
function counter(){
  let counter = 0
  return function () {
    return counter++
  }
}

const con = counter()

console.log(con()) // 0
console.log(con()) // 1
console.log(con()) // 2
console.log(con()) // 3
console.log(con()) // 4
```
