# Closures

Closures in JavaScript dienen dazu, eine Funktion zusammen mit dem umgebenden Zustand (Variablen, Parameter) zu kapseln. Sie ermöglichen es, dass die innere Funktion auf Variablen aus dem äußeren Kontext zugreifen kann, selbst nachdem die äußere Funktion bereits beendet wurde. Dies ist besonders nützlich, weil es einen Mechanismus für Datenkapselung und -speicherung bietet.

```javascript
// Funktion counter erstellt und gibt eine Zählfunktion zurück
function counter() {
  let counter = 0;

  // Die zurückgegebene Funktion ist eine Closure
  return function () {
    return counter++;
  };
}

// Die Variable con erhält die Zählfunktion durch Aufruf der counter-Funktion
const con = counter();

// Jeder Aufruf von con() erhöht den Zähler und gibt den aktuellen Wert zurück
console.log(con()); // Gibt 0 aus
console.log(con()); // Gibt 1 aus
console.log(con()); // Gibt 2 aus
console.log(con()); // Gibt 3 aus
console.log(con()); // Gibt 4 aus

```
In diesem Beispiel ist die innere Funktion, die von counter zurückgegeben wird, die Closure. Sie behält Zugriff auf die Variable counter aus dem umgebenden Kontext der äußeren Funktion, auch nachdem die äußere Funktion bereits abgeschlossen wurde. Dadurch kann der Zähler bei jedem Aufruf von con() weiterhin aktualisiert werden.

Hier sind einige Gründe, warum Closures nützlich sind:
- Datenkapselung: Closures ermöglichen es, Daten privat zu halten, indem sie den Zugriff auf Variablen auf den Gültigkeitsbereich der Funktion beschränken. Dies hilft, Konflikte mit globalen Variablen zu vermeiden und fördert den sicheren Umgang mit Daten.

- Erhaltung des Zustands: Closures ermöglichen Funktionen, sich den Zustand zu merken, in dem sie erstellt wurden. Dies ist besonders hilfreich für Funktionen, die über längere Zeiträume hinweg existieren müssen und auf konsistenten Zustand zugreifen müssen.

- Dynamische Funktionsgenerierung: Closures erlauben es, Funktionen dynamisch zu generieren und zurückzugeben, basierend auf bestimmten Bedingungen oder Eingaben. Dies führt zu flexiblerem und wiederverwendbarem Code.

- Callback-Funktionen: In JavaScript werden Closures häufig bei der Verwendung von Callback-Funktionen verwendet. Die äußere Funktion kann Informationen für die innere Funktion bereitstellen, auch wenn die äußere Funktion bereits abgeschlossen ist.
