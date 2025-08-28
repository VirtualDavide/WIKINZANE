2025-03-06 21:36

Tags : [[Java]] [[ServerSideDevelopment]]

# JSP - Java Server Page

Una pagina **JSP** è rappresentata  da codice HTML con incapsulate al suo interno delle direttive **JSP**, racchiuse in una pagina in particolare rag `<% %>`, rappresentanti codice Java. A differenza delle servlet, dove e necessario compilare il codice Java, con le pagine **JSP** la compilazione *avviene in automatico*, al momento del caricamento della pagina stessa che deve avere estensione `.jsp`.

Infatti alla prima richiesta di una pagina jsp il server effettuerà i seguenti passi: 
1. **estrae** il codice Java e crea la servlet (*JSP engine*)
2. **Invia** alla nuova classe la richiesta Http arrivatogli e viene generata una risposta.
3. **spedisce** la pagina risultante al browser.

## Il motivo
L'introduzione del **JSP** è stata fatta per semplificare il lavoro dei **Web Designer** che potevano così dedicarsi al layout della pagina senza entrare in merito della logica di gestione dell'applicazioni.

## References

- [[Servlet]]
- [[JavaBean]]
- [[Tag in una pagina JSP]]