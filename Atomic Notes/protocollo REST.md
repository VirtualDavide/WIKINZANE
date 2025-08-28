2025-03-21 10:42

Tags : [[WebServices]]

# protocollo REST

**REST** è un approccio alternativo a **SOAP** , molto più leggero ed efficace, poiché si basa sulla corrispondenza diretta tra:
- oggetti remoti da leggere/scrivere individuati mediante *Uniform Resource Identifiers* (URI).
- comandi **Http** da applicare agli oggetti.

**REST** è un modo semplice per organizzare le interazioni tra sistemi indipendenti poiché **non prevede esplicitamente nessuna modalità per descrivere come interagire con una risorsa** : le operazioni sono implicite del protocollo Http.

Le interazioni tra client e server devono essere senza stato (*stateless*).

### I principi dell'architettura REST
Secondo l'approccio REST i principi che rendono il WEB adatto a realizzare *Web Service* si possono riassumere nei seguenti cinque : 
1. *identificazione delle risorse tramite URI.*
2. *utilizzo esplicito dei metodi Http.*
3. *risorse autodescrittive.*
4. *collegamenti tra risorse con interazioni stateless.*
5. *comunicazioni senza stato in XML, JSON o entrambi.*

### Principali differenza tra REST e SOAP
Le principali differenze di REST rispetto a SOAP sono:
1. un *WS REST* è **incentrato sulla risorsa**, mentre un *WS SOAP* è incentrato sul servizio.
2. un *WS REST* gestisce le risorse accessibili con **chiamate Http**, mentre un *WS SOAP* è incentrato sul servizio.
3. in REST si ha una **riduzione della parte di configurazione** e nei parametri di controllo.
## References

- [[Architettura SOA]]
- [[Web Service]]
- [[protocollo SOAP]]
- [[Metodi HTTP]]
- [[RESTFull]]