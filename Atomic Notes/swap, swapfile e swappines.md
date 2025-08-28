2025-02-13 17:18

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]]

# swap, swapfile e swappines

La memoria **swap** è uno spazio su in disco rigido che viene utilizzata come estensione della **RAM**. Quando la RAM fisica è piena e il sistema ha bisogno di più memoria per eseguire programmi o gestire dati, il sistema operativo può spostare temporaneamente alcune informazioni dalla RAM al file di swap sul disco.

Normalmente su Linux la swap risiede o in una partizione o in un file. 

Con il comando `swaponn -s` possiamo vedere quali partizione swap sono attive nel nostro sistema. Lo stesso risultato possiamo averlo visualizzando il contenuto di `/proc/swaps`.

La memoria da dedicare come area di swap può variare, in genere dovrebbe essere x1.5 rispetto alla memoria RAM. Ovviamente tale discorso non vale quando abbiamo molta RAM installata (16GB in poi...).
## Creazione e attivazione della memoria swap (parted)

Avviamo **parted** sulla partizione dove vogliamo aggiungere lo swap : 
```bash
sudo parted /dev/<nomedeldisco>
```

Creiamo la nuova partizione di swap : 
```
mkpart <nomedellapartizione> linux-swap <inizioPartizione> <finePartizione>
```

Impostiamo il tipo di partizione su swap : 
```
set <nomedellapartizione> swap on
```

Usciamo dall'interfaccia interattiva di `parted` con il comando `quit`.
## Creazione e attivazione della memoria swap (fdisk)

Avviamo **fidisk** sul disco dove vogliamo creare le partizioni : 
```bash
sudo fdisk /dev/<nomedeldisco>
```

**Creiamo** la partizione : 
- premi `n` per creare una nuova partizione
- scegli `p` per una partizione primaria
- scegli il numero della partizione
- specifichiamo inizio e fine della partizione

**Cambiamo** il tipo di partizione (*default = ext4*):
- premi `t` per cambiare il tipo
- Inserisci il numero della partizione che abbiamo creato
- digita `82` per impostare il tipo su Linux Swap

**Salviamo** le modifiche digitando `w`.

(*fdsik non ci chiederà che tipo di tabella delle partizioni creare, perchè funziona solo su sistemi MBR*)

## Formattazione della nuova memoria

Per far **utilizzare la memoria al sistema operativo e avvisarlo** della nuova partizione, dobbiamo digitare i comandi : 
```bash
sudo mkswap /dev/<nomedeldisco> //formata la partizione come swap
sudo swapon /dev/<nomedeldisco> //attiva la nuova area di swap
```

## References

- [[Parted(mkpart)]]
- [[Priorità memoria Swap]]
