2025-06-13 16:40

Tags : [[Esame di Stato]]

# VPN - la completezza

Una VPN (Virtual Private Network) **è una rete privata creata all'interno di**
**un’infrastruttura di rete pubblica**, per esempio internet.

*Ma perché abbiamo sentito l’esigenza di implementare questa tecnologia ?* 

Come detto prima per poter accedere alle risorse presenti all'interno di un’azienda, o **ci si doveva recare fisicamente lì** oppure l’azienda stessa doveva investire nella costruzione di **rete privata attraverso canali dedicati ad uso esclusivo**, pagandone l’affitto al proprietario o al gestore della linea. Ovviamente anche se era molto vantaggioso dal punto di vista delle prestazioni, poiché si aveva un canale esclusivo per le proprie trasmissioni, questo richiedeva un grande investimento iniziale e onerosi costi di manutenzione. Ed è proprio **in questo contesto che nascono le VPN**; proprio per estendere geograficamente la propria rete LAN aziendale. 

In commercio esistono due tipi di VPN :

- **Remote access VPN** : consente ai singoli utenti di stabilire dalla loro rete domestica ad esempio una connessione con la rete aziendale. Gli utenti connessi possono accedere quindi alle risorse aziendali proprio come se fossero lì.

- **Site to Site VPN** : permetti di stabilire connessioni sicure attraverso internet ad intere sedi. La rete centrale di una sede può essere condivisa con un’altra sede dislocata altrove, come se fossero geograficamente vicine.

Ecco che quindi la differenza sta in proprio in questo, **poiché una collega utenti ad**
**una rete privata mentre l’altra collega due reti private tra di loro**. La VPN Sito to Site
in particolare può essere **intraned-based** se una società vuole unire le diverse reti
LAN delle sue sedi in un’unica rete privata o **exstranet-based** se per esempio viene
collegata un rete locale aziendale con la LAN di un’altra azienda, magari proprio
perché hanno un rapporto stretto di interessi economici o logistici.

Indipendentemente dalla tipologia di VPN ci sono due componenti indispensabili per
la gestione degli accessi alle reti private. Il primo è un server di accesso alla rete, ovvero un NAS. Al server NAS arrivano le richieste di accesso alla VPN e questo può utilizzare il proprio processo di autenticazione o il alternativa si avvale di un server di autenticazione separato come per esempio un **RADIUS AAA** Server. Le 3 A presenti nell'acronimo riassumono i 3 servizi che un server RADIUS fornisce quali :

1. **autenticazione** (conferma chi sei)
2. **autorizzazione** (identifica ciò che ti è permesso fare)
3. **accounting** (tiene traccia della nostra attività quando siamo connessi)

L’altro componente fondamentale è proprio un software VPN client che ci permette
di interagire con il server VPN. 

A rendere ancora più sicure le reti VPN ci sono alcuni protocolli atti al proteggere ogni pacchetto trasmesso nel suo viaggio in internet. **Tali protocolli vengono definiti di protocolli di tunneling**. Grazie a questi un intero pacchetto viene posto all'interno di un altro pacchetto prima di essere trasportato su internet. Il pacchetto esterno protegge il contenuto dalla vista del pubblico e assicura che il pacchetto passeggero si muova all'interno di un tunnel virtuale. Ovviamente il messaggio all'interno dei pacchetti viene crittografato per non essere comprensibile nel caso in cui dovesse essere prelevato.

Ma ecco che tecnologie come le VPN, i firewall, la crittografia, non nascono solo nei
nostri tempi, anzi la sicurezza delle trasmissioni è tema che da secoli affrontiamo
come essere umani. Uno degli avvenimenti più emblematici in questo contesto è
proprio l’elaboratore costruito da Alan Turig per decifrare le comunicazioni
tedesche nel 1940.

La sicurezza informatica nasce proprio in contesto bellico
## References

- [[Home Server -  Docker e Docker compose]]
- [[La seconda Guerra Mondiale - La completezza]]