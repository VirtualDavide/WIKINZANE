Creation Date: 2025-09-15 
Creation Time: 21:46
Author: [[feb]]

## Container e macchine virtuali

### Definizione di Container e Differenze:

Docker, Podman e simili sono noti come container engine.
Un container è un'unità standard di software che **impacchetta il codice e tutte le sue dipendenze**, consentendo di eseguire l'applicazione in modo rapido e affidabile in ambienti diversi.

 Le macchine virtuali (VM) eseguono un sistema operativo completo con il proprio kernel, mentre i container non eseguono un kernel separato.
Le VM **richiedono un hypervisor** per gestire l'hardware virtualizzato, mentre i container comunicano direttamente con il kernel del sistema operativo host.

### Overhead e Performance:
Le VM hanno un overhead maggiore a causa della necessità di eseguire più kernel e gestire l'hypervisor, il che può ridurre le performance.
I container riducono l'overhead, migliorando le performance grazie all'assenza di un kernel separato.

Le risorse allocate a un container possono essere modificate in tempo reale senza downtime, a differenza delle VM che richiedono un riavvio per modifiche hardware.
Questo consente una maggiore flessibilità nella gestione delle risorse.

### Isolamento e Sicurezza:
Le VM offrono un isolamento più forte rispetto ai container, poiché ogni VM è un'istanza separata di hardware virtuale.
I container hanno un isolamento più debole; un bug nel container engine potrebbe consentire a un'applicazione malevola di accedere al sistema host o ad altri container.

 I processi all'interno di un container possono essere visti come normali processi dal sistema operativo host, poiché i container sono gruppi di processi.

## REFERENCES
- [[Che cos'è Docker ?]]
- [[Docker e Podman - concetti e terminologia]]
## TAGS
- [[Docker]]