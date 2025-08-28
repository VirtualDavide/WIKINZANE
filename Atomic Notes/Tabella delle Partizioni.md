2025-01-21 16:28

Tags : [[Installazione di Linux e Package Management]] / [[102.1]]

# Tabella delle Partizioni

La **tabella delle partizioni** in Linux è una struttura dati che **definisce come è suddiviso un disco rigido** o un altro dispositivo di memorizzazione in partizioni.

Ogni partizione può essere usata per vari scopi, come l'installazione di sistemi operativi, la memorizzazione di dati o la creazione di ambienti di sviluppo.

I principali tipi di partizione sono : 
- **MBR**(*Master Boot Record*) : È il formato tradizionale, per la tabella delle partizioni. Supporta fino a 4 partizioni primarie oppure 3 partizioni primarie ed uno estesa che può contenere ulteriori partizioni logiche. MBR ha un limite di dimensione di 2TB per le partizioni.
- **GPT**(*GUID Partition Table*) : **È un formato moderno che fa parte dello standard UEFI**. Supporta un numero molto maggiore di partizione (fino a 128 in Windows) e consente partizioni di dimensioni superiori a 2 TB.

La tabella delle partizioni è fondamentale per il funzionamento del sistema operativo, poiché consente al kernel di Linux di identificare e gestire le diverse partizioni e i file system in esse contenuti. Puoi visualizzare e modificare le partizioni utilizzando strumenti come `fdisk`, `parted` o `gparted`

## Problemi con le partizioni
Se per qualche motivo dovessimo eliminare per sbaglio una partizione, non dobbiamo disperare. Infatti abbiamo solo cancellato l'etichetta che aveva una determinata area del disco, ma non i dati all'interno di esso, quindi per recuperare la partizione o la tabella delle partizioni non basterà altro che ricrearle come prima.
## References

- [[Parted (partizionamento Dischi)]]