2024-12-12 21:47

Tags :
# Codici di Stato

I **codici di stato**, sono codici restituito da server HTTP per indicare al client, l'esito di una richiesta. Sono stati definiti dall'**IETF** (*Interneet Engeniring Task Force*).

Il codice di stato è formato da 3 cifre la cui prima, indica la **classe di appartenenza**, mentre le altre due indicano la risposta specifica.

I codici da : 
- **100-199** (*information*) : forniscono informazioni temporanee della richiesta (viene sconsigliato il loro utilizzo).
- **200-299** (*Successful*) : richiesta avvenuta con successo.
- **300-399** (*Redirection*) : Reindirizzare la richiesta, non è errore. (*google e molti altri inviano questi codice, proprio perché la richiesta a google.com non viene fatta su un solo server, ma viene renderizzata in quelli sparsi per il globo*).
- **400-499** (*Client Error*) : Condizioni di errore provocate dal comportamento del client.
- **500-599** (*Server Error*) : problemi verificatisi sul server.

Codici di stato più comuni  : 

![[Pasted image 20241212215909.png]]

*rfc2616*
## References

- [[HTTP]]