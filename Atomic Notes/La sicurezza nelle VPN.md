2025-02-12 18:52

Tags : [[VPN]]

# La sicurezza nelle VPN

I fattori che rendono sicuro l'utilizzo delle VPN sono 3 : 
1. **autenticazione** 
2. **cifratura**
3. **tunneling**

## Autenticazione
Si definisce **autenticazione dell'identità** il processo con cui **un sistema informatico**, un applicativo o un utente **verifica la corretta identità** di un altro sistema informatico, un applicativo o un **utente** che vuole comunicare attraverso una connessione per poi concedergli **l'autorizzazione a usufruire dei relativi servizi associati**.

La procedura per connettersi una VPN in genere è sempre a **più fattori**.

Una volta effettuato l'accesso al sistema informatico, questo stesso fornirà l'accesso solo alle risorse a cui è autorizzato, tale procedura viene chiamata **accounting**.

(*la gestione dell'autenticazione è spesso affidata ad un server NAS o ad uno dedicato come server AAA*)
## Cifratura 
Le VPN utilizzano una vasta gamma di sistemi crittografici per cifrare i pacchetti che vengono inviati all'interno della rete virtuale. Nel caso specifico delle VPN viene sopratutto utilizzato il protocollo **Internet Key Exchange**; il suo compito principale è quello di implementare lo scambio delle chiavi per cifrare i pacchetti.

Il protocollo IKE viene utilizzato nelle reti ipv4.


## References

- [[Tunneling e Trasporto ]]