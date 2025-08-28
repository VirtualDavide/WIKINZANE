2025-04-04 15:36

Tags : [[Docker]]

# Modalità di Networking - Drivers

Il networking in Docker è un aspetto **fondamentale che consente ai container di comunicare tra loro e con l'esterno**. Sebbene possa sembrare semplice, offre una notevole flessibilità e diverse opzioni di configurazione. I principali tipi di networking, noti anche come driver, sono *Bridge, Host e Null*.

### Tipi di Networking

#### Rete Null
La rete Null è un'opzione che **isola completamente il container dalla rete**. In pratica, il container non ha accesso a nessuna rete, rendendolo piuttosto limitato e poco utile per la maggior parte delle applicazioni.

#### Rete Host
La rete Host consente al container di **condividere l'interfaccia di rete con il sistema host**. In questo modo, non c'è alcun isolamento tra il container e l'host. Qualsiasi applicazione in esecuzione all'interno del container ha accesso diretto alla scheda di rete dell'host, come se fosse in esecuzione direttamente sul sistema operativo. 
#### Rete Bridge
La rete Bridge è il driver più interessante e comunemente utilizzato. **Fornisce un livello di isolamento tra i container e l'host**, consentendo la creazione di reti virtuali con uno **spazio di indirizzamento separato**. Questo permette ai container di comunicare tra loro in modo privato o semi-privato, senza interferire con la rete fisica dell'host. 

## References

- [[Esporre (non esporre un servizio)]]
- [[Reti Virtuali - Docker]]