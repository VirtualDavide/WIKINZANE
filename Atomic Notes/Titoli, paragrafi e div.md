2025-01-23 16:47

Tags : [[HTML]]

# Titoli, paragrafi e div

## Titoli
In HTML, i titoli sono definiti utilizzando i tag da `<h1>` a `<h6>`, dove `<h1>` rappresenta il titolo principale e `<h6>` il titolo meno importante. Ecco un esempio:

```HTML
<h1>Benvenuti nel mio sito web</h1>
<h2>Chi siamo</h2>
<h3>I nostri servizi</h3>
<h4>Servizio 1</h4>
<h5>Dettagli del servizio 1</h5>
<h6>Contatti</h6>
```

## Paragrafi 
I paragrafi sono definiti utilizzando il tag `<p>`. Ecco un esempio di come si possono utilizzare i paragrafi:

```HTML
<p>Questo è un paragrafo che introduce il contenuto del sito. Qui puoi trovare informazioni utili e interessanti.</p>

<p>Il nostro obiettivo è fornire servizi di alta qualità ai nostri clienti. Siamo impegnati a garantire la massima soddisfazione.</p>
```

## Div
I **div** (abbreviazione di "division") sono un elemento fondamentale in HTML utilizzato per raggruppare e organizzare contenuti all'interno di una pagina web. Il tag `<div>` è un contenitore generico che non ha un significato semantico specifico

```HTML
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Esempio di Div</title>
    <style>
        .header {
            background-color: #f1f1f1;
            padding: 20px;
            text-align: center;
        }
        .content {
            display: flex;
        }
        .main {
            flex: 70%;
            padding: 20px;
        }
        .sidebar {
            flex: 30%;
            background-color: #f9f9f9;
            padding: 20px;
        }
        .footer {
            background-color: #f1f1f1;
            text-align: center;
            padding: 10px;
            position: relative;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>

    <div class="header">
        <h1>Benvenuti nel mio sito web</h1>
    </div>

    <div class="content">
        <div class="main">
            <h2>Contenuto Principale</h2>
            <p>Questo è il contenuto principale della pagina. Qui puoi inserire testi, immagini e altri elementi.</p>
        </div>
        <div class="sidebar">
            <h2>Barra Laterale</h2>
            <p>Questa è una barra laterale. Puoi usarla per link, informazioni aggiuntive o pubblicità.</p>
        </div>
    </div>

    <div class="footer">
        <p>Copyright © 2023</p>
    </div>

</body>
</html>
```

## References

- [[Il linguaggio HTML]]