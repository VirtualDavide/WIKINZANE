2025-03-21 10:21

Tags : [[WebServices]]

# Architettura SOA

Con la creazione di sempre più servizi Web era necessario definire un architettura standard. Nasca così la *Service Oriented Architecture* (SOA).

L'architettura SOA deve fornire una piattaforma per costruire servizi applicativi aventi le seguenti caratteristiche : 

- **loosely coupled** : l'utente del servizio non deve preoccuparsi di scegliere con quali servizi comunicare, "ci pensa" l'infrastruttura.
- **location transparent** : l'infrastruttura deve nascondere quanti più dettagli tecnici possibili, relative alle tecnologie tra loro differenti.
- **protcol independet** : deve essere possibile aggiornare in qualunque momento le implementazioni, senza modificare le interfaccie.
**
Gli attori della SOA sono 3 :

1. **Service Consumers** : richiede un servizio interrogando il **Server Registry**;
2. **Service Registry** : esso contiene le repository dei servizi e fornisce al consumers la descrizione dell'interfaccia del servizio.
3. **Service Provider** : Esso una volta che il client conosce l'interfaccia, accetta le richiesta da quest'ultimo, le elabora ed invia la risposta.

Naturalmente affinchè un servizio sia disponibile deve essere pubblicata nel **Service Registry** dal **Service Provider** una copia della descrizione del servizio.
## References

- [[Web Service]]