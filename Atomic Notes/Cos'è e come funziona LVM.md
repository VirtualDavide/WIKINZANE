2025-04-20 21:16

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]]

# Cos'è e come funziona LVM

Il _Logical Volume Manager_, spesso abbreviato in **LVM**, rappresenta uno strumento fondamentale nella gestione avanzata dello storage su Linux, grazie alla sua capacità di introdurre un livello di astrazione tra il sistema operativo e l'hardware fisico. In pratica, LVM permette di superare i limiti imposti dalle dimensioni e dalla configurazione fisica dei dischi, offrendo una flessibilità straordinaria sia in termini di espansione che di gestione.

Alla base della logica di LVM ci sono tre concetti fondamentali: i **Physical Volumes (PV)**, i **Volume Groups (VG)** e i **Logical Volumes (LV)**. I *Physical Volumes* rappresentano i dischi fisici o le partizioni su cui si costruisce l’intero sistema LVM. Un insieme di questi dischi può essere aggregato in un *Volume Group*, che funge da contenitore logico. Su questo contenitore si creano infine i *Logical Volumes*, che vengono formattati e montati nel sistema operativo proprio come normali partizioni. Tutto questo avviene in modo completamente trasparente per l’utente e per le applicazioni, che continuano a interagire con le partizioni come se fossero standard.

Uno dei principali vantaggi di LVM è la **gestione flessibile dello spazio**: è possibile espandere o ridurre un volume logico senza interrompere il servizio o riavviare il sistema. Se, per esempio, un server web necessita improvvisamente di più spazio, è sufficiente aggiungere un nuovo disco fisico (PV), estendere il Volume Group e successivamente il Logical Volume. Tutto ciò avviene a **sistema attivo**, senza downtime.

Un altro punto di forza è la **possibilità di spostare i dati a caldo**. Questo significa che si possono migrare i dati da un disco a un altro mentre il sistema è operativo. Se un disco sta per essere sostituito, si può semplicemente istruire LVM a spostare i dati contenuti su di esso verso un altro dispositivo disponibile, e una volta completato lo spostamento, rimuovere fisicamente il disco senza impattare le applicazioni o interrompere i servizi.

Inoltre, LVM consente di incrementare le prestazioni grazie allo **striping**, una tecnica simile a quella utilizzata nel RAID 0. Quando si dispone di più dischi, i dati possono essere scritti in parallelo su ciascuno di essi, suddividendoli a blocchi, in modo da aumentare la velocità complessiva di lettura e scrittura.

Infine, LVM supporta anche la creazione di **snapshot**. Questo permette di catturare uno stato del volume in un determinato momento, utile per operazioni di backup, test o verifica dell’integrità dei dati. Gli snapshot sono creati a caldo, senza fermare il sistema, rendendo le operazioni di backup e disaster recovery molto più semplici da gestire e meno invasive.

## References

- [[LVM - aggiungere e rimuovere dischi]]