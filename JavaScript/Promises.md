# Promises

Eine Promise-Funktion erwartet immer eine Funktion als Argument, die zwei Parameter hat: resolve und reject (reject ist dabei Optional). Diese Parameter sind Funktionen, die aufgerufen werden, um den Status des Promises zu ändern.
Die resolve-Funktion wird aufgerufen, wenn die asynchrone Ausführung erfolgreich abgeschlossen wurde. Der Rückgabewert der resolve-Funktion wird als Erfolgswert des Promises verwendet.
Die reject-Funktion wird aufgerufen, wenn ein Fehler aufgetreten ist. Der Rückgabewert der reject-Funktion wird als Fehlerwert des Promises verwendet.
Durch die Verwendung von Promises können asynchrone Operationen in JavaScript einfacher und lesbarer gestaltet werden.

### Beispiele
##### Anonymous-Function
```javascript
let promise = new Promise(function (resolve, reject) { 
    // Hier passiert etwas, das etwas Zeit braucht
    let x = 20;
    if (x > 10) {
        resolve(x);
    } else {
        reject("Zu niedrig");
    }
});
```
##### Arrow-Anonymous-Function
```javascript
let promise = new Promise((resolve, reject) => { 
    // Hier passiert etwas, das etwas Zeit braucht
    let x = 20;
    if (x > 10) {
        resolve(x);
    } else {
        reject("Zu niedrig");
    }
});
```
##### Function mit Parameterübergabe
```javascript
function promise(x){
  return new Promise((resolve, reject) => { 
    // Hier passiert etwas, das etwas Zeit braucht
    if (x > 10) {
        resolve(x)
    } 
    else{
      reject("Zu niedrig")
    }
  });
}
```
##### Nutzung der Promise
```javascript
promise.then(
    function (value) {
        console.log("Erfolgreich:", value);
    },
    function (error) {
        console.log("Fehler:", error);
    }
);
```
##### Nutzung der Promise mit Parameter und Arrow-Function und Then/Catch
```javascript
promise(12)
  .then((value) => {
    console.log("Erfolgreich:", value)
  })
  .catch((error) => {
      console.log("Fehler:", error)
  }
)
```
