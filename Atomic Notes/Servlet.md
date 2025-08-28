2025-01-14 16:06

Tags : [[ServerSideDevelopment]] - [[Java]]

# Servlet

Un alternativa al modello CGI può essere il linguaggio Java mediante le **servlet** (*classi Java*). La principale differenza tra servlet e CGI è chi script **CGI** sono eseguiti dal sistema operativo, e quindi sono potenzialmente **meno portabili** delle servelt, che essendo scritte in Java, vengono eseguite dalla JVM, integrata nel Web Server stesso.

Inoltre una seconda grande differenza è gli **script CGI, devono essere ogni volta caricati in memoria,** ogni volta che vengono chiamati mentre **le servlet vengono caricate solo una volta** e successivamente sarà un thread a gestire ogni ogni richiesta.
## La struttura  e l'esecuzione di una Servlet
Una servlet è una classe *speciale*, così definita direttamente dalla **Sun** : 

> [!NOTE] Java Servlet Specification v.2.4
> Una **servlet** è un componente software scritto in Java, gestito da un **container**, che produce contenuto Web dinamico

Ogni istanza di una **servlet è un oggetto Java che viene caricato ed eseguito dal Web Server** all'interno del processo di richiesta/risposta di servizi. 

Il suo **controllo** viene effettuato da un'altra applicazione Java, **il container**, che r**egola il ciclo di vita della servlet** stessa. 

In realtà è il **Web Server** stesso che svolge la funzione di **container** occupandosi della gestione di vita della servlet, **passandogli i dati del client e restituendo al client i dati prodotti dall'esecuzione della servlet**.

Il flusso di esecuzione quindi è : 
1. un **client** invia una richiesta per una servlet a un Web application server;
2. se si tratta di una prima richiesta allora il server istanzia e carica la servlet;
3. si attiva un **thread** che gestisce la comunicazione tra il **client** e la **servlet**;
4. il **server** invia al **threadServlet** la richiesta prevenutagli dal **client**;
5. il **threadServlet** costruisce ed imposta la risposta e la inoltra al server;
6. il server **invia** la risposta al client.

*l'ambiente di esecuzione è detto container e nel caso in cui si verifichi più richieste contemporaneamente vengono attivati nel **servlet container*** *più thread*. 
## Tomcat
Il **server container** open source più diffuso e utilizzato è **Tomcat**, del gruppo **Apache**. **Tomcat** è un server container *open source* e *free software* integramente scritto in **Java** disponibile per diverse piattaforme che **si integra con i più diffusi Web Server**, come Apache e IIS.
## References

- [[Common Gateway interface (CGI)]]
- [[Ciclo di vita di una Servlet]]
- [[Connessione Database - Servlet]]
- [[Vantaggi e Svantaggi delle Servlet]]
- [[Sessioni e Cookie]]
- [[Apache server]]
- [[Tomcat]]