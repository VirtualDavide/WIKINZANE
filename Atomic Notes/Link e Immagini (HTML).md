2025-01-23 16:58

Tags : [[HTML]]

# Link e Immagini (HTML)

### Link 
I link in HTML sono creati utilizzando il tag `<a>` (ancora), che consente di collegare il contenuto a un'altra pagina web, a un'altra sezione della stessa pagina o a un'email. I link sono fondamentali per la navigazione su Internet e migliorano l'esperienza dell'utente.
#### Link Esterni
I link esterni puntano a pagine web che si trovano al di fuori del tuo sito. Per creare un link esterno, utilizzi l'attributo `href` per specificare l'URL della pagina di destinazione.

**Esempio di Link Esterno:**
```HTML
<a href="https://www.example.com">Visita il nostro sito</a>
```

#### Link Interni a un'altra Pagina del Sito
I link interni collegano a un'altra pagina all'interno dello stesso sito. Puoi utilizzare un percorso relativo o assoluto per specificare la pagina di destinazione.

**Esempio di Link Interno a un'altra Pagina:**
```HTML
<a href="pagina2.html">Vai alla Pagina 2</a>
```
#### Link a una Sezione della Stessa Pagina
Per creare un link che punta a una sezione specifica della stessa pagina, devi prima definire un'**ancora** utilizzando l'attributo `id` su un elemento HTML. Poi, puoi creare un link che punta a quell'ID.

**Esempio di Link a una Sezione della Stessa Pagina:**
```HTML
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Esempio di Link Interni</title>
</head>
<body>

    <h1>Benvenuti nel nostro sito</h1>

    <p><a href="#sezione1">Vai alla Sezione 1</a></p>
    <p><a href="#sezione2">Vai alla Sezione 2</a></p>

    <h2 id="sezione1">Sezione 1</h2>
    <p>Questo è il contenuto della Sezione 1.</p>

    <h2 id="sezione2">Sezione 2</h2>
    <p>Questo è il contenuto della Sezione 2.</p>

</body>
</html>
```

## Immagini
Per inserire un'immagine, si utilizza il tag `<img>`. Questo tag ha un attributo `src` che specifica il percorso dell'immagine e un attributo `alt` che fornisce un testo alternativo per l'immagine (*utile per l'accessibilità e nel caso in cui l'immagine non venga caricata*).

**Esempio di Immagine:**
```HTML
<img src="https://www.example.com/immagine.jpg" alt="Descrizione dell'immagine" width="300" height="200">
```

## References

- [[Il linguaggio HTML]]