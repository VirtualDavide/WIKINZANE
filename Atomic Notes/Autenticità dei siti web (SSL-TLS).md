2025-01-07 23:48

Tags : [[Crittografia]] - [[Web]]

# Autenticità dei siti web (SSL-TLS)

Comunemente noti come certificati SSL/TLS, svolgono un ruolo cruciale nell'autenticazione dei siti web e nella protezione dei dati trasmessi tra il browser dell'utente e il server del sito.

### Che cosa sono i certificati SSL/TLS ?

I certificati **SSL** (*Secure Socket Layer*) e **TLS** (*Transport Layer Security*) sono file digitali che collegano una chiave crittografica a un'organizzazione o a un individuo.

### Tipi di certificati 

Esistono vari tipi di certificati, ognuno con caratteristiche specifiche : 

- **Certificati Domain Validation (DV)** : Questi certificati offrono un livello base di autenticazione. Vengono emessi dopo che il richiedente ha dimostrato di avere il controllo sul dominio.

- **Certificati Organization Validation (OV)**: Questi certificati forniscono un livello di autenticazione più elevato. Oltre a verificare il controllo del dominio, l'autorità di certificazione (CA) verifica anche l'esistenza legale dell'organizzazione richiedente. Sono adatti per siti web aziendali e commerciali.

- **Certificati Extended Validation (EV)**: Questi certificati offrono il massimo livello di autenticazione. L'emissione richiede una verifica approfondita dell'identità dell'organizzazione, inclusi documenti legali e informazioni aziendali. I siti web con certificati EV mostrano un indicatore di sicurezza verde nella barra degli indirizzi del browser, aumentando la fiducia degli utenti.

### Funzionamento dei certificati SSL/TLS

- **Handshake SSL/TLS**: Quando un utente visita un sito web protetto da SSL/TLS, il browser e il server eseguono un processo chiamato "handshake". Durante questo processo, il server invia il certificato SSL/TLS al browser, che verifica la validità del certificato.
    
- **Verifica del certificato**: Il browser controlla se il certificato è stato emesso da un'autorità di certificazione affidabile, se è ancora valido (non scaduto) e se il dominio corrisponde a quello del certificato. Se tutte le verifiche hanno esito positivo, il browser stabilisce una connessione sicura.
    
- **Crittografia**: Una volta stabilita la connessione, i dati trasmessi tra il browser e il server vengono crittografati, proteggendo le informazioni da intercettazioni e attacchi.
## References

- 