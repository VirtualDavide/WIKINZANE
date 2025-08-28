2025-04-20 20:56

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]] / [[DailyLinux]]

# Partizionamento e montaggio d'emergenza (var)

Supponiamo ora di avere una situazione concreta: ci accorgiamo che la directory `/var` sta crescendo troppo, magari perché ospita molti log, file temporanei o database. La root `/` è quasi piena e vogliamo spostare `/var` su un’altra partizione, magari su un disco nuovo appena collegato, ad esempio `/dev/sdb`.

La prima cosa da fare è verificare che il disco sia riconosciuto dal sistema, usando il comando `lsblk`, che ci mostra tutti i dischi e le relative partizioni. Se vediamo una voce `/dev/sdb` senza partizioni, possiamo crearne una usando `fdisk /dev/sdb`. Dentro `fdisk`, creiamo una nuova partizione con `n`, confermiamo con Invio le opzioni predefinite, e poi scriviamo `w` per salvare le modifiche.

Una volta usciti da `fdisk`, creiamo il file system sulla nuova partizione con:

```bash
mkfs.xfs /dev/sdb1
```

Usiamo `xfs`, ma potremmo scegliere anche `ext4` a seconda delle preferenze. A questo punto, creiamo un punto di mount temporaneo:

```bash
mkdir /mnt/nuovo_var
mount /dev/sdb1 /mnt/nuovo_var
```

Ora bisogna spostare tutti i contenuti della vecchia `/var` nella nuova partizione. Lo facciamo con `rsync`, che mantiene permessi, owner e struttura:

```bash
rsync -avx /var/ /mnt/nuovo_var/
```

Verifichiamo che tutto sia stato copiato correttamente. Se è tutto a posto, rinominiamo la vecchia `/var` per tenerla come backup temporaneo:

```bash
mv /var /var.old
```

Poi creiamo una nuova `/var` vuota:

```bash
mkdir /var
```

Montiamo finalmente la nuova partizione al suo posto:

```bash
mount /dev/sdb1 /var
```

Controlliamo che tutto funzioni. Se il sistema non dà errori, possiamo rendere il cambiamento permanente modificando il file `/etc/fstab`. Aggiungiamo una riga in fondo:

```bash
/dev/sdb1  /var  xfs  defaults  0 0
```

Fatto questo, possiamo riavviare e verificare che `/var` sia montato correttamente con `df -h`. Dopo qualche giorno, se tutto funziona senza problemi, possiamo anche rimuovere la vecchia `/var.old` con:

```bash
rm -rf /var.old
```

In questo modo, abbiamo liberato spazio sulla root, isolato `/var` su una partizione dedicata – migliorando sia la gestione che la stabilità del sistema – e il tutto è stato fatto a sistema in funzione, senza reinstallare nulla. Questo è il tipo di intervento che trasforma un amministratore ordinario in uno consapevole, capace di agire con precisione e senza panico.
## References

- [[Struttura file system Linux]]