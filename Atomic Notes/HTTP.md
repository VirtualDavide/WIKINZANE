2024-12-12 20:11

Tags : [[Web]] #computerScience

# HTTP

HTTP (Hyper Text Trasfer Protocol) è un protocollo che consente di inviare e ricevere risorse dal Web, come documenti, pagine html, immagini, audio ecc, da un host chiamato Client ad un altro host chiamato Server. 

Una risorsa viene identificata da un URI. 

Durante una comunicazione HTTP vengono scambiati messaggi di richiesta e di risposta.

I **messaggi di richiesta** sono formati da : 
1. riga di richiesta. (*metodo,URI,versione HTTP*)
2. intestazione (*header*).
3. corpo del messaggio.

esempio  : *GET /percorso/file.html HTTP/1.1*

I **messaggi di risposta** sono formati da  :
1. riga iniziale (*versione HTTP e stato*).
2. intestazione (*header*) - (*facoltativa*).
3. corpo (*facoltativo*).

esempio : *HTTP/1.1 200 OK {header - corpo}*

Il protocollo HTTP per comunicare utilizza vari metodi come : 
- *GET*;
- *HEAD*;
- *POST*;
- *PUT*;
- *DELETE*;
- *OPTIONS*;
- *TRACE*;

Un metodo è uno dei più importanti aspetti di una richiesta HTTP, in quanto rappresenta "l'intenzione" del client presente nella richiesta al server.
## References

- [[Client]]
- [[Server]]
- [[URI]]
- [[Conversazione client e server]]
- [[Metodi HTTP]]
- [[Codici di Stato]]