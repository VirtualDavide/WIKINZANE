2025-04-20 21:20

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]] / [[DailyLinux]]

# LVM - aggiungere e rimuovere dischi

La gestione dello spazio su disco in ambiente Linux può essere resa estremamente dinamica attraverso l’utilizzo del Logical Volume Manager (LVM), che permette di astrarre il livello fisico dell’archiviazione e lavorare in modo flessibile con dischi, partizioni e file system. Questo sistema consente di aggiungere nuovi dischi, estendere o ridurre volumi logici, spostare dati e rimuovere unità fisiche, tutto senza interrompere i servizi attivi.

Una volta identificata la necessità di espandere un file system – ad esempio perché lo spazio nella root è limitato – si può verificare la situazione attuale con:

```bash
df -hT
```

Successivamente, dopo aver collegato un nuovo disco, si controlla il dispositivo assegnato con:

```bash
fdisk -l
```

Si entra nel disco identificato per creare una nuova partizione:

```bash
fdisk /dev/sdb
```

All'interno di `fdisk`, si esegue:

- `n` per nuova partizione
- `p` per primaria
- selezione della partizione 1
- conferma dei settori iniziali e finali (default)
- `t` per cambiare tipo
- `8e` per impostare il tipo LVM
- `w` per scrivere le modifiche

Dopo la creazione, si inizializza la nuova partizione come Physical Volume:

```bash
pvcreate /dev/sdb1
```

Si verifica che sia stato riconosciuto:

```bash
pvscan
```

Ora si estende un Volume Group già esistente, ad esempio chiamato `cl`, con:

```bash
vgextend cl /dev/sdb1
```

E si controlla lo stato del VG:

```bash
vgdisplay
```

Per visualizzare i volumi logici esistenti:
```bash
lvscan
```

A questo punto, si può procedere all’espansione del Logical Volume (LV) corrispondente alla root. Prima si verifica il nome esatto del volume logico con `lvscan`, poi si utilizza il comando `lvextend -L +8G /dev/mapper/nomeLV` per estenderlo di 8 gigabyte (oppure si può usare `-l +100%FREE` per utilizzare tutto lo spazio disponibile nel VG). Dopo l’estensione del volume logico, il file system deve essere ridimensionato per sfruttare lo spazio aggiunto, con `resize2fs /dev/mapper/nomeLV`.

LVM consente anche lo spostamento dei dati da un disco a un altro, utile ad esempio quando si vuole rimuovere un disco fisico. Prima di rimuoverlo, si utilizza `pvmove /dev/sdb1`, che sposta tutti i dati presenti su quel physical volume su altri dischi presenti nel volume group. Una volta completato lo spostamento, il disco può essere escluso dal volume group con `vgreduce nomeVG /dev/sdb1`, e infine rimosso dal sistema LVM con `pvremove /dev/sdb1`.

È anche possibile ridurre la dimensione di un logical volume, ad esempio con `lvreduce -L -8G /dev/mapper/nomeLV`, ma questa operazione è delicata e va fatta solo dopo aver verificato che lo spazio non sia occupato dai dati. Una volta ridotto il volume, sarà possibile liberare spazio nel volume group o spostare dati più facilmente.
## References

- [[Cos'è e come funziona LVM]]