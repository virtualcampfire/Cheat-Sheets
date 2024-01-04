# JavaScript Map Cheat Sheet

## Erstellen einer Map
```javascript
const myMap = new Map();
```
Hinzufügen von Schlüssel-Wert-Paaren
```javascript
myMap.set("Schlüssel1", "Wert1");
myMap.set("Schlüssel2", "Wert2");
```
Abrufen eines Werts anhand des Schlüssels
```javascript
const wert1 = myMap.get("Schlüssel1"); // wert1 enthält "Wert1"
const wert2 = myMap.get("Schlüssel2"); // wert2 enthält "Wert2"
```
Überprüfen, ob ein Schlüssel vorhanden ist
```javascript
const keyExist = myMap.has("Schlüssel1"); // true
```
Löschen eines Schlüssel-Wert-Paars
```javascript
myMap.delete("Schlüssel1"); // Entfernt das Schlüssel-Wert-Paar mit dem Schlüssel "Schlüssel1"
```
Iterieren über eine Map
```javascript
// Mit for...of
for (const [key, value] of myMap) {
  console.log(`Schlüssel: ${key}, Wert: ${value}`);
}

// Mit forEach
myMap.forEach((value, key) => {
  console.log(`Schlüssel: ${key}, Wert: ${value}`);
});

```
Weitere Hinweise
- Maps sind nützlich für Schlüssel-Wert-Paare und bieten effiziente Such- und Aktualisierungsmöglichkeiten.
- Maps erlauben die Verwendung beliebiger Datentypen als Schlüssel.
- Maps sind ideal, wenn die Schlüssel nicht aufeinanderfolgende Werte haben oder komplexe Datentypen sind.
