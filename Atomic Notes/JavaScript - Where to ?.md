2025-05-30 22:18

Tags : [[JavaScript]]

# JavaScript - Where to ?

Certo, ecco la spiegazione integrata con i tre metodi per referenziare uno script JavaScript esterno:

Gli script JavaScript vengono inseriti all'interno delle tag `<script>`, che rappresentano il loro "ambiente" all'interno della struttura HTML.

A titolo esemplificativo, il seguente script modifica il contenuto di un elemento con ID "demo":

```html
<script>
  function changeText() {
    document.getElementById("demo").innerHTML = "Hello JavaScript!";
  }
</script>
```

Per quanto riguarda il posizionamento degli script all'interno della pagina HTML, l'utente può scegliere di collocarli all'interno della sezione `<head>` oppure della sezione `<body>`, o anche in entrambe le sezioni.

Esempio di script posizionato nella sezione `<head>`:

```html
<!DOCTYPE html>
<html>
<head>
  <title>JavaScript in Head</title>
  <script>
    function changeText() {
      document.getElementById("demo").innerHTML = "Hello JavaScript!";
    }
  </script>
</head>
<body>
  <h1>JavaScript in Head</h1>
  <p id="demo">This is a demonstration.</p>
  <button onclick="changeText()">Click me</button>
</body>
</html>
```

Posizionare gli script all'interno della sezione `<head>` comporta che essi vengano eseguiti prima del caricamento del contenuto della pagina, il che potrebbe rallentare il caricamento complessivo.

Esempio di script posizionato nella sezione `<body>`:

```html
<!DOCTYPE html>
<html>
<head>
  <title>JavaScript in Body</title>
</head>
<body>
  <h1>JavaScript in Body</h1>
  <p id="demo">This is a demonstration.</p>
  <button onclick="changeText()">Click me</button>
  <script>
    function changeText() {
      document.getElementById("demo").innerHTML = "Hello JavaScript!";
    }
  </script>
</body>
</html>
```

Posizionare gli script all'interno della sezione `<body>` consente di eseguirli man mano che la pagina viene caricata, migliorando così l'esperienza dell'utente.

Un'ulteriore opzione è l'utilizzo di script JavaScript esterni, referenziati mediante l'attributo `src` all'interno della tag `<script>`. Esistono tre metodi principali per referenziare uno script esterno:

1. Utilizzo di un URL completo:
   ```html
   <script src="https://example.com/script.js"></script>
   ```
2. Utilizzo di un percorso relativo:
   ```html
   <script src="script.js"></script>
   ```
3. Utilizzo di nessun percorso (se lo script è nella stessa directory):
   ```html
   <script src="script.js"></script>
   ```

L'utilizzo di script esterni consente di mantenere il codice organizzato e riutilizzabile, oltre a permettere il caching da parte del browser per un caricamento più veloce. **È importante ricordare che negli script esterni non devono essere inserite ulteriori tag** `<script>`.

La scelta della posizione ottimale per gli script JavaScript e del metodo di referenziamento dipende dalle esigenze specifiche del progetto, bilanciando fattori come il caricamento della pagina, la riusabilità del codice e l'organizzazione complessiva.
## References

- [[JavaScript - Introduzione]]
- [[JavaScript - Output]]