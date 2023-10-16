# JavaScript Canvas Cheat Sheet

## Einstieg

Um mit Canvas zu beginnen, musst du ein Canvas-Element in deiner HTML-Datei erstellen:

```html
<canvas id="meinCanvas"></canvas>
```


Du kannst dann eine Referenz auf das Canvas-Element in deinem JavaScript-Code erhalten:
```javascript
const canvas = document.getElementById('meinCanvas');
```

## Formen zeichnen

### Rechtecke

Um ein Rechteck auf dem Canvas zu zeichnen, kannst du die Methoden fillRect oder strokeRect verwenden:

```javascript
// Rechteck füllen
context.fillRect(x, y, breite, höhe);

// Rechteck umranden
context.strokeRect(x, y, breite, höhe);
```


### Kreise

Um einen Kreis auf dem Canvas zu zeichnen, kannst du die Methode arc verwenden:

```javascript
context.beginPath();
context.arc(x, y, radius, startWinkel, endWinkel);
context.fill();
```

### Linien

Um eine Linie auf dem Canvas zu zeichnen, kannst du die Methoden moveTo und lineTo verwenden:

```javascript
context.beginPath();
context.moveTo(x1, y1);
context.lineTo(x2, y2);
context.stroke();
```


## Formen stylen

### Farben

Um die Füll- oder Umrandungsfarbe einer Form festzulegen, kannst du die Eigenschaften fillStyle oder strokeStyle verwenden:

```javascript
context.fillStyle = 'rot';
context.strokeStyle = 'blau';
```

### Transparenz

Um die Transparenz einer Form festzulegen, kannst du die Eigenschaft globalAlpha verwenden:

```javascript
context.globalAlpha = 0.5;
```


### Linienbreite

Um die Linienbreite einer Form festzulegen, kannst du die Eigenschaft lineWidth verwenden:

```javascript
context.lineWidth = 2;
```


## Transformationen

### Translation

Um das Canvas zu verschieben, kannst du die Methode translate verwenden:

```javascript
context.translate(x, y);
```


### Rotation

Um das Canvas zu rotieren, kannst du die Methode rotate verwenden:
```javascript
context.rotate(winkel);
```


### Skalierung

Um das Canvas zu skalieren, kannst du die Methode scale verwenden:

```javascript
context.scale(skalaX, skalaY);
```


### Text

Um Text auf dem Canvas zu zeichnen, kannst du die Methoden fillText oder strokeText verwenden:

```javascript
context.fillText(text, x, y);
context.strokeText(text, x, y);
```


### Text stylen

Um den Text zu stylen, kannst du die Eigenschaften font, textAlign und textBaseline verwenden:

```javascript
context.font = 'fett 24px Arial';
context.textAlign = 'center';
context.textBaseline = 'middle';
```


### Bilder

Um ein Bild auf dem Canvas zu zeichnen, kannst du die Methode drawImage verwenden:

```javascript
const image = new Image();
image.src = 'pfad/zum/bild.png';
image.onload = () => {
  context.drawImage(image, x, y, breite, höhe);
};
```


## Animation

Um eine Animation auf dem Canvas zu erstellen, kannst du die Methode requestAnimationFrame verwenden:

```javascript
function animate() {
  // Canvas aktualisieren
  // ...

  requestAnimationFrame(animate);
}

requestAnimationFrame(animate);
```
