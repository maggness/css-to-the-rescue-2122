# CSS Vuurwerkshow

Om deze show mogelijk te maken ben ik aan de slag gegaan met css variabelen, keyframes en selectoren.

## Mijn uitwerking

Vuurwerkshow met een kleine puzzel die je kan doen om het “grote mannen vuurwerk” te kunnen zien.

Je ziet knoppen voor je waarmee je de show kunt activeren, maar dat is niet het enige wat je kunt doen. Als je specifieke items indrukt kan je het grote “grote mannen vuurwerk” activeren, wat een wat permanentere show geeft.

### Idee week 1

Ik wil een kijkdoos maken waar je in het klein een show ziet. Je drukt op een punt en een mannetje loopt dan naar dat punt om vuurwerk aan te steken. Het gaat er een beetje uitzien als paper mario, witte uitsnedes en 2d items die op een 3d plane lopen.

Ik heb de binnenkant van de doos gemaakt, dit door middel van `transform-style: preserve-3d;` en `perspective: 25vh;`
Dan via `transform-origin: center bottom;` & `transform: rotateX(90deg);` op de zijkanten om de rotatie op de juiste plek te zetten en 3d te draaien.

Ook ben ik met `@keyframes` gaan spelen voor het grote mannen vuurwerk. Ik wil hier animaties achter elkaar laten spelen om zo een wat complexere show op te zetten. Hier ga ik later ook interactie aan toevoegen.

![V1 BOX](https://user-images.githubusercontent.com/30145681/156364272-d9c6b363-339c-4295-b7d0-ccd544c56289.png)


### Idee week 2

Ik ga 3 vuurwerk pijlen maken met css variabelen om hiermee te experimenteren. Ik heb een soort template gemaakt voor elke pijl, waar ik alleen de translated verander per pijl.
```css
/* Firework arrow template */
.vuurwerkContainer ul {
  padding: 0;
  margin: 0;
  height: 0.4em;
  width: 0.4em;
  position: fixed;
  list-style: none;
  transform-origin: bottom;
  bottom: var(--vuurwerkPijlPositieBottom);
  left: var(--vuurwerkPijlPositieLeft);
  z-index: var(--vuurwerkPijlzIndex);
  background-color: var(--vuurwerkPijlColor);
  animation: vuurwerkPad var(--vuurwerkPijlAnimatie) forwards ease-in;
}
```

En geef ik per pijl de positie, kleur enzv.
```css
/* Firework arrow variations */
.vuurwerkContainer ul:first-of-type {
  --vuurwerkPijlPositieLeft: 20%;
  --vuurwerkPijlPositieBottom: 13%;
  --vuurwerkPijlzIndex: 11;
  --vuurwerkPijlColor: black;
  --vuurwerkPijlAnimatie: 2s;
  --ColorFirework: blue;
}
```

