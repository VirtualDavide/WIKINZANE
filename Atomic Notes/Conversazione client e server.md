2024-12-12 20:37

Tags :

# Conversazione client e server

Ogni conversazione tra client e server sul Web inizia con una request (richiesta) rappresentata da un messaggio in formato HTTP creato dal client. Invia la richiesta al server e ne attende la risposta.

Il protocollo HTTP utilizza come protocolli di trasporto il TCP.

Nella connessione HTTP 1.1 venne introdotta la connessione **permanente**. Il server al contrario di HTTP 1.0 non chiude subito la connessione una volta esaudita la richiesta, ma utilizza sempre la stessa per le ulteriori richieste.

Esistono due tipi di connessione permanente : 
- **incanalata** : Le richieste vengono messe in una cosa chiamata **pipeline** e vengo processato mano mano nell'ordine in cui sono state inviate.
- **non incanalata** : Il client passa ad una nuova richiesta solo quando quella precedente è stata esaudita.
## References

- [[HTTP]]