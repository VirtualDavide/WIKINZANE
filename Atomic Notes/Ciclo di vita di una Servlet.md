2025-01-30 18:03

Tags : [[ServerSideDevelopment]] - [[Java]]

# Ciclo di vita di una Servlet

## *init()*
Al momento del caricamento della **servlet** in memoria, il **container** (*tomcat*), invoca il metodo `init()` che provvede all'inizializzazione della servlet e al settaggio della sue variabili globali in modo da renderla disponibile per la prima richiesta.

Il metodo `init()` riceve come parametro un oggetto `ServletConfig` che contiene la configurazione iniziale della servlet.

## *service()*
Il metodo `service()`, è chiamato ogni volte che il client richiede una servlet. In base al metodo utilizzato per la richiesta, il metodo `service()` invoca la funzione `doGet()` o `doPost()`, che gestiscono le richieste mediante i due oggetti : `Http request` (*contiene i parametri inviati dal client, il riferimento alla sessione ecc.*) e `Http response` (*contiene la risposta per il client, permettendo di inviare la pagina HTML di risposta*).

## *destroy()*
La terminazione di una **servlet** avviene tramite il metodo `destroy()`.
*(possiamo utilizzarlo per salvare tutte quelle informazioni che possono essere utili al prossimo avvio della servlet stessa)*
## References

- [[Servlet]]