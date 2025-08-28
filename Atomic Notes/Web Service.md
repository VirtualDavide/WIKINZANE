2025-03-20 11:53

Tags : [[WebServices]]

# Web Service

Un **Web Service** rappresenta la disponibilità di un servizio attraverso il **Web**, come per esempio le prenotazioni online di un biglietto aereo : le disponibilità del posto vengono restituite grazie a un collegamento in tempo reale, in quanto le compagnie aeree espongono i dati dei voli (orari, posti, tariffe, ecc) attraverso una **API** che il server interroga con la tecnica del **Web Service**.

> [!NOTE] API
> Le API (acronimo di Application Programming Interface), ovvero interfaccia di programmazione delle applicazioni; sono set di definizioni e protocolli con i quali vengono realizzati e integrati software applicativi

Per poter far comunicare il **client** (*Service Consumers*) con il **server** *Service Provider* al quale viene inviata una richiesta, è necessario avere a disposizione : 
- un **medium**, cioè uno strumento di comunicazione, come per esempio il protocollo **Http**.
- un **formato**, cioè una lingua interpretabile da diverse applicazioni, come per esempo **XML** o **JSON**.

Un web Service è quindi un sistema software progettato per l'intestazione tra i diversi elaboratori in rete; tale caratteristica si ottiene associando all'applicazione un'interfaccia software che espone il servizio all'esterno.

I messaggi di richiesta possono avere un formato particolare e sono sempre incapsulati e trasportati tramite i protocolli del Web (*http*).

> [!NOTE] Differenza sostanziale
> Il contenuto di un **sito Web** è creato per fare in modo che un **essere umano** possa leggerlo e capirlo, mentre un **servizio Web** è una comunicazione fra **due computer**.

Per avvenire tale comunicazione ad oggi le tecnologie più usate sono : 
- Web Service **SOAP** (*medium HTTP (POST) e formato XML*).
- Web Service **REST** (*medium HTTP (POST,GET,PUT,DELETE) e formato XML, JSON, Text*).

## References

- [[Web Services e API - La nascita]]
- [[Architettura SOA]]
- [[protocollo SOAP]]
- [[protocollo REST]]
- [[Connessione Database - Servlet]]