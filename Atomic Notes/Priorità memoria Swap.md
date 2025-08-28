2025-02-13 18:27

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]]

# Priorità memoria Swap

## Priorità generale
Una volta creata e attivata la memoria Swap, possiamo cambiare la sua priorità al volo, modificando il file `/proc/sys/vm/swappiness `. 

Possiamo modificarlo a volo con `nano`, o con `echo` per esempio : 
```bash
echo "0" > /proc/sys/vm/swappiness
```

Il valore (0-100) rappresenta l'aggressività della memoria swap, infatti se il numero e uguale a **0** significa che il SO utilizzerà la memoria swap solo ed esclusivamente la memoria RAM si riempissi completamente, mentre se sarà uguale a **100** il sistema scriverà la maggior parte dei dati presenti nella RAM nella memoria di swap.

## Priorità per ogni area
Con il comando `swapon -s` possiamo vedere un elenco delle memoria swap attive e la loro priorità. Possiamo cambiare la priorità di utilizzo del sistema con i seguenti comandi : 
```bash
swapoff /dev/<nomedeldisco>
swapon /dev/<nomedeldisco> -p <valoredellepriorità>
```

Più è alto il valore che impostiamo, più quell'area sarà utilizzata dal SO.

La modifica comunque non è permanente e per renderla dobbiamo modificare il file `/etc/fstab`.

Per prima cosa all'interno del file dovremmo aggiungere il nome del disco dell'area che vogliamo sia utilizzata. Potremmo riferirci a quest'ultima con `/dev/<nomedeldisco>`, ma per essere più sicuri sarebbe ottimale riferirci al disco con il suo UUID (*Universal Unique Identifier*).

Ricaviamo tale numero con il comando : 
```bash
sudo blkid /dev/<nomedeldisco>
```

Una volta ricavato possiamo copiarlo e andare a modificare il file `/etc/fstab`, aggiungendo la seguente riga : 

```
UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx none swap sw 0 0
```

1. **UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx:
    - Questa colonna specifica l'UUID (Universally Unique Identifier) della partizione. L'UUID è un identificatore unico per il filesystem, che rimane costante anche se il dispositivo cambia nome. In questo caso, identifica la partizione di swap.
2. **none**:
    - Questa colonna indica il punto di montaggio. Poiché si tratta di una partizione di swap, non è necessario specificare un punto di montaggio (come `/mnt` o `/home`), quindi viene utilizzato `none`.
3. **swap**:
    - Questa colonna specifica il tipo di filesystem. In questo caso, indica che si tratta di una partizione di swap.
4. **sw**:
    - Questa colonna contiene le opzioni di montaggio. L'opzione `sw` indica che il dispositivo deve essere utilizzato come swap. Ci sono altre opzioni che possono essere specificate qui, ma `sw` è quella standard per le partizioni di swap.
5. **0**:
    - Questa colonna è utilizzata per il backup con il comando `dump`. Un valore di `0` indica che la partizione non deve essere sottoposta a backup.
6. **0**:
    - Questa colonna è utilizzata per determinare l'ordine in cui le partizioni devono essere controllate all'avvio con il comando `fsck`. Un valore di `0` indica che non è necessario controllare questa partizione.
## References

- [[swap, swapfile e swappines]]