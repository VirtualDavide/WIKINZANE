2025-01-23 20:40

Tags : [[HTML]]

# Query String

La query string è una parte di URL che contiene dati da inviare a un server web. Viene utilizzata principalmente nei moduli HTML per inviare informazioni al server quando un utente invia un modulo.

La query string inizia dopo il simbolo di domanda (`?`) nell'URL e può contenere uno o più parametri, separati da un simbolo di (`&`).

**Struttura della query string**
```URL
https://www.example.com/pagina?parametro1=valore1&parametro2=valore2
```

La query string comunque invia dati in **chiaro** proprio perchè questi possono essere letti chiaramente dall'URL, per questo quando si devono inviare dei dati sensibili è estremamente consigliato utilizzare il metodo "POST". Tale metodo infatti non trasmette i dati in chiaro con la query string.
## References

- [[Form e invio dei dati al server]]
- [[Metodi HTTP]]