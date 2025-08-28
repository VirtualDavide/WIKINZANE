2024-12-13 10:42

Tags : [[Crittografia]]

# Crittografia a chiave asimmetrica

La crittografia a chiave asimmetrica (*o a chiave pubblica*), nasce per risolvere il problema della **distribuzione sicura delle chiavi**. Essa utilizza due chiavi per ciascun soggetto, una **privata** nota solo al soggetto, l'altra **pubblica**, distribuita a tutti i possibili soggetti con cui il primo vuole comunicare in sicurezza.

La crittografia garantisce 3 aspetti fondamentale nella trasmissione delle informazioni: 

1. **confidenzialità** (*chiavi del destinatario*): Poiché solo il destinatario conosce la sua chiave privata, un ascoltatore non può essere in grado di decifrare la trasmissione. 
2. **autenticazione** (*chiavi del mittente*): Il destinatario sarà certo dell'identità del mittente da cui ha ricevuto il testo cifrato perché solo la chiave pubblica avuta dal mittente stesso riesce a decifrare quel testo.
3. **integrità** : Poiché entrambi i soggetti usano le proprie chiavi private, è garantito anche che il messaggio non sia stato alterato.

## Passaggi crittografia asimmetrica

1. testo in chiaro 
2. algoritmo di cifratura (*chiave privata del mittente*)
3. testo cifrato
4. algoritmo ci cifratura (*chiave pubblica del destinatario*)
5. testo cifrato
6. algoritmo di decifratura (*chiave privata del destinatario*)
7. testo cifrato
8. algoritmo di decifratura (*chiave pubblica del mittente*)
9. testo in chiaro

Per poter cifrare un testo con una chiave e poi decifrarlo con una chiave completamente diversa al fine di riottenere il testo di partenza, occorre che le due chiavi **siano matematicamente correlate**.
## References

- [[Sistemi crittografici]]
- [[Crittografia a chiave simmetrica]]
- [[RSA (Rivest,Shamir,Adleman)]]
- [[Posta Certificata (PEC)]]
- [[Firma Digitale]]
- [[Sistemi di identificazione digitale]]-