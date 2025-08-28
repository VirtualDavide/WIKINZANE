2025-07-26 23:07

Tags : [[DailyLinux]] [[RAID]]

# mdadm - rimuovere e aggiungere un nuovo disco per sostituire un disco guasto

Se uno dei dischi si è guastato e desideri **rimuovere e sostituire** il disco guasto, segui questi passaggi

**Identifica il Disco Guasto**
Controlla lo stato dell'array per identificare il disco guasto:
```bash
sudo mdadm --detail /dev/md0
```

**Rimuovi il Disco Guasto** (*segnalare il disco come fallito in caso*)
Supponendo che il disco guasto sia `/dev/sdX`, rimuovilo dall'array con:
```bash
sudo mdadm /dev/md0 --remove /dev/sdX
```

**Collega il Nuovo Disco**
Installa fisicamente il nuovo disco che sostituirà quello guasto.

**Aggiungi il Nuovo Disco all'Array** 
Aggiungi il nuovo disco (ad esempio, `/dev/sdY`) all'array:
```bash
sudo mdadm /dev/md0 --add /dev/sdY
```

**Controlla il Progresso della Ricostruzione**
Monitora la ricostruzione dell'array con:
```bash
cat /proc/mdstat
```

*Quando bisogna aggiungere nuovi dischi a un array RAID, non è necessario partizionarli manualmente prima di aggiungerli all'array. È possibile aggiungere dischi non partizionati direttamente all'array RAID. `mdadm` gestirà automaticamente la configurazione del disco all'interno dell'array. Una volta che il disco è stato aggiunto all'array, `mdadm` si occuperà della formattazione e della configurazione necessaria per integrarlo nel RAID.*
## References

- [[mdadm - aggiungere un disco per aumentare la capienza]]
- [[mdadm - RAID managing]]