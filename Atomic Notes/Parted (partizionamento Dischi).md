2025-01-21 17:17

Tags : [[Installazione di Linux e Package Management]] / [[102.1]]

# Parted (partizionamento Dischi)


`parted` è un potente strumento per la gestione delle partizioni in Linux. 

## Comandi utili
Avviamo `parted` passando come argomento il disco che vogliamo partizionare.
```bash
sudo parted /dev/sdx
```
(*con il comando entriamo in modalità interattiva*)

**Visualizzare le informazioni sul disco** : 
```bash
print
```

**Creare una nuova tabella delle partizioni**
*MBR*
```bash
mklabel msdos
```

*GPT*
```bash
mklabel gpt
```

**Creare una nuova partizione**
```bash
mkpart <nomePartizione> <tipo_file_system> <inizio> <fine>
```
*esempio*
```
mkpart primary ext4 1Mib 100Gib
```

**Eliminare una partizione**
```bash
rm <numero della partizione>
```

**Ridimensionare una partizione**
```bash
resizepart <numeroPartizione> <nuovaFine>
```

**Uscire da parted**
```
quit
```

## Ridimensionamento partizione
Quando ridimensioniamo una partizione è importante, ridimensionare anche il suo file system contenuto in essa per evitare problemi di integrità. Ecco come puoi farlo su Linux : 

(1) **smontare la partizione** : prima di ridimensionare, è necessario smontare la partizione. Se la partizione è in uso, potrebbe essere necessario farlo da ambiente live, (*come una live USB di Linux*).
```bash
sudo umont /dev/sdx
```

(2) **ridimensionare il file system**
```bash
sudo resize2fs /dev/sdX <nuovaDimensione>
sudo resize2fs /dev/sdX 8GB
```

(3) **Adesso passiamo al ridimensionamento della partizione con `parted`**
```bash
sudo parted /dev/sdX
(parted) resizepart <numero_partizione> <nuovo_fine>
```

(4) **Rimontare la partizione**
```bash
sudo mount /dev/sdx /mnt
```
## References

- [[Tabella delle Partizioni]]
- [[Parted(mkpart)]]
- [[Parted(esempio pratico)]]
- [[Dispositivi in Linux]]