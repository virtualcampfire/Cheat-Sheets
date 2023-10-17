# Switch Statement

```javascript
switch (ausdruck) {
  case wert1:
    // Code-Block, der ausgeführt wird, wenn ausdruck gleich wert1 ist
    break;
  case wert2:
    // Code-Block, der ausgeführt wird, wenn ausdruck gleich wert2 ist
    break;
  default:
    // Code-Block, der ausgeführt wird, wenn ausdruck keinen der vorherigen Werte entspricht
}
```
- switch wird verwendet, um zwischen verschiedenen Optionen basierend auf dem Wert eines Ausdrucks zu wählen.
- Der ausdruck wird nur einmal ausgewertet und mit jedem wert in den case-Anweisungen verglichen.
- Wenn der ausdruck mit einem wert übereinstimmt, wird der zugehörige Code-Block ausgeführt.
- Die break-Anweisung wird verwendet, um den Code-Block zu verlassen und mit der Ausführung des restlichen Codes fortzufahren.
- Wenn kein wert mit dem ausdruck übereinstimmt, wird der Code-Block unter default ausgeführt (falls vorhanden).
