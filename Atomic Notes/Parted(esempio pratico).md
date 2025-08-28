2025-01-22 14:22

Tags :   [[Installazione di Linux e Package Management]] / [[102.1]] / [[DailyLinux]]

# Parted(esempio pratico)

Ecco come puoi creare una nuova tabella delle partizioni GPT e tre partizioni (*una per UEFI in FAT32, una in ext4 e una per la swap*) utilizzando `parted`. Assicurati di avere un backup dei dati importanti, poiché la creazione di una nuova tabella delle partizioni cancellerà tutte le partizioni esistenti sul disco.

(1)**Avvia `parted`** : Apri il terminale e avvia `parted` sul disco desiderato : 
```bash
sudo parted /dev/sdx
```

(2)**Creazione della tabelle delle partizioni** (*GPT*) :
```parted
mklabel gpt
```

(3)**Creazione di una partizione UEFI e flag di boot** :
```parted
mkpart prymary fat32 1Mib 513Mib
set 1 esp on
```

(4) **Creazione di una partizione per il file system** : 
```parted
mkpart primary ext4 513MiB 996Gib
```

(5) **Creazione della partizione per la memoria swap** : 
```parted
mkpart primary linux-swap 996Gib 1000Gib
```

(6) **Uscire da `parted`** : 
```parted
quit
```

## Formattazione delle partizioni 
Una volta che abbiamo creato tutte le partizioni necessarie, dobbiamo formattarle per il loro corretto funzionamento : 

**Formata la partizione UEFI** : 
```bash
sudo mkfs.fat -F32 /dev/sdx
```

**Formattazione file system** (*ext4*) :
```bash
sudo mkfs.ext4 /dev/sdx
```

## Swap
Quando crei una partizione di swap con `parted`, stai semplicemente riservando uno spazio sul disco. Tuttavia, questo spazio non è ancora configurato per essere utilizzato come swap. Il comando `mkswap` inizializza la partizione di swap, creando la struttura necessaria affinché il sistema operativo possa gestirla correttamente.

**Creazione della memoria si swap** : 
```bash
sudo mkswap /dev/sdx
```

**Attivare la partizione di swap** :
```bash
sudo swapon /dev/sdx
```

## References

- [[Parted (partizionamento Dischi)]]