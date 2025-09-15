Creation Date: 2025-09-15 
Creation Time: 21:48
Author: [[feb]]

## Docker e Podman - concetti e terminologia

 Introduzione ai termini chiave: immagini, container, Docker Hub, Dockerfile, Docker Compose.
### Differenza tra Immagine e Container
- **Container**: Processo o gruppo di processi in esecuzione isolata sul sistema operativo tramite il container engine.
- **Immagine**: Eseguibile che avvia il container, simile a un file system di una distribuzione Linux con applicativi e dipendenze.

### Caratteristiche delle Immagini Docker
- Dalla stessa immagine possiamo avviare più container (*es. più istanze di Apache*).
- Le immagini sono composte da diversi layer, ognuno dei quali aggiunge nuove funzionalità o dipendenze.

###  Struttura di un Dockerfile
 Il Dockerfile è la "ricetta" per costruire un'immagine Docker.
- Esempio di Dockerfile: utilizzo di Ubuntu come base, installazione di Apache e copia di file necessari.

### Vantaggi dell'Utilizzo dei Layer
- Efficienza nella gestione delle dipendenze: condivisione di layer comuni tra diverse immagini.
- Risparmio di spazio su disco evitando la duplicazione di librerie e file.

### Gestione di più Container con Docker Compose
- Introduzione a Docker Compose per definire e gestire più container in un file di configurazione.
- Vantaggi: avvio, arresto e gestione semplificata di stack complessi (es. LAMP).

Il container in esecuzione è la nostra torta, l'immagine sono tutti gli ingredienti messi sul tavolo, pronti per essere impastati, il docker file è la ricetta che stabilisce di quali ingredienti abbiamo bisogno.
## REFERENCES
- [[Che cos'è Docker ?]]
- [[Registry e Repository]]
## TAGS
- [[Docker]]