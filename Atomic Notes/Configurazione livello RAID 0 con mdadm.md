2025-07-26 21:33

Tags : [[DailyLinux]] [[RAID]]

# Configurazione livello RAID 0 con mdadm

https://www.digitalocean.com/community/tutorials/how-to-create-raid-arrays-with-mdadm-on-ubuntu
### Creazione di un RAID 0 

- **requisiti** : 2 dispositivi di memorizzazione
- **vantaggio primario** : prestazioni in termini di lettura/scrittura e capacità.
- **Cosa da tenere a mente** : backup funzionali. Un singolo errore del dispositivo distruggerà tutti i dati nell'array.

#### Identificazione dei dispositivi dei componenti
Identificare i dischi grezzi disponibili : 
```bash
lsblk -o NAME,SIZE,FSTYPE,MOUNTPOINT
```

```bash
//output
NAME     SIZE FSTYPE   TYPE MOUNTPOINT
sda      100G          disk <--
sdb      100G          disk <--
vda       25G          disk 
├─vda1  24.9G ext4     part /
├─vda14    4M          part 
└─vda15  106M vfat     part /boot/efi
vdb      466K iso9660  disk 
```

#### Costruzione del RAID 0
Passare i componenti disponibili al comando `mdadm --create`. Bisogna specificare il nome del dispositivo che si vuole creare, il livello RAID e il numero di dispositivi. 
```bash
sudo mdadm --create --verbose /dev/md0 --level=0 --raid-devices=2 /dev/sda /dev/sdb
```

Confermare che il RAID è stato creato con successo controllando il `proc/mdstat`
```bash
cat /proc/mdstat
```

```bash
//Output
Personalities : [linear] [multipath] [raid0] [raid1] [raid6] [raid5] [raid4] [raid10] 
md0 : active raid0 sdb[1] sda[0]
      209584128 blocks super 1.2 512k chunks
            
            unused devices: <none>
```

Questo output rivela che il `dev/md0` il dispositivo è stato creato nella configurazione RAID 0 utilizzando il `/dev/sda` e così via `/dev/sdb`.

*Aspettare che finiscano tutti i processi, prima di effettuare cambiamenti al file system o al RAID stesso.*

#### Creare e montare file system

Creazione del file system
```bash
sudo mkfs.ext4 -F /dev/md0
```

Creazione del punto di montaggio per allegare il nuovo file system
```bash
sudo mkdir -p /mnt/md0
```

Montare il file system
```bash
sudo mount /dev/md0 /mnt/md0
```

Verificare il nuovo spazio disponibile 
```bash
df -h -x devtmpfs -x tmpfs
```

```bash
//output
Filesystem      Size  Used Avail Use% Mounted on
/dev/vda1        25G  1.4G   23G   6% /
/dev/vda15      105M  3.4M  102M   4% /boot/efi
/dev/md0        196G   61M  186G   1% /mnt/md0
```

Il nuovo file system è ora montato e accessibile.
## References

- [[RAID - cos'è, a cosa serve e come funziona]]
- [[mdadm - RAID managing]]