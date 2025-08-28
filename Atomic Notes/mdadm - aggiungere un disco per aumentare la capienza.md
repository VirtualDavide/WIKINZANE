2025-07-26 23:00

Tags : [[DailyLinux]] [[RAID]]
# mdadm - aggiungere un disco per aumentare la capienza

Se desideri **aggiungere un nuovo disco** per aumentare la capienza del tuo array RAID 5, segui questi passaggi:

**Collega il Nuovo Disco**: Assicurati che il nuovo disco sia fisicamente installato e riconosciuto dal sistema.

**Aggiungi il Disco all'Array**: Utilizza il comando seguente per aggiungere il nuovo disco (ad esempio, `/dev/sdY`) all'array:
```bash
sudo mdadm /dev/md0 --add /dev/sdY
```

**Ridimensiona l'Array**
Dopo aver aggiunto il disco, dovrai ridimensionare l'array per includere il nuovo disco:
```bash
sudo mdadm --manage /dev/md0 --grow --raid-devices=numero_finale_dischi
```

**Controlla il Progresso della Ricostruzione**: Puoi monitorare il progresso della ricostruzione con:
```bash
cat /proc/mdstat
```

*Quando bisogna aggiungere nuovi dischi a un array RAID, non è necessario partizionarli manualmente prima di aggiungerli all'array. È possibile aggiungere dischi non partizionati direttamente all'array RAID. `mdadm` gestirà automaticamente la configurazione del disco all'interno dell'array. Una volta che il disco è stato aggiunto all'array, `mdadm` si occuperà della formattazione e della configurazione necessaria per integrarlo nel RAID.*

## References

- [[mdadm - RAID managing]]