2025-05-30 22:26

Tags : [[JavaScript]]

# JavaScript - Output

JavaScript offre diverse modalità per visualizzare i dati, ognuna con le proprie caratteristiche e utilizzi:

1. **innerHTML()**: Permette di modificare il contenuto di un elemento HTML esistente, identificato tramite il suo ID. È molto utile per aggiornare dinamicamente il contenuto di una pagina web.

Esempio:
```javascript
document.getElementById("demo").innerHTML = "Hello World!";
```

2. **document.write()**: Scrive direttamente nell'output del documento HTML. Attenzione, però: se utilizzato dopo il caricamento della pagina, sovrascriverà l'intero contenuto.

Esempio:
```javascript
document.write("Hello World!");
```

3. **alert()**: Visualizza un messaggio in una finestra di dialogo. Utile per brevi notifiche, ma da non abusare per non irritare l'utente.

Esempio:
```javascript
alert("Hello World!");
```

4. **console.log()**: Invia un messaggio alla console del browser, utile per il debug del codice senza interferire con l'esperienza utente.

Esempio:
```javascript
console.log("Hello World!");
```

Infine, viene menzionato anche il metodo **window.print()**, che permette di stampare direttamente la pagina web corrente.
## References

- [[JavaScript - Where to ?]]
- [[JavaScript - Sintassi]]