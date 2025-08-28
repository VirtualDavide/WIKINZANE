2025-07-26 21:36

Tags : [[DailyLinux]] [[RAID]]

# mdadm - RAID managing

**mdadm** è una potente utility a riga di comando utilizzata principalmente nei sistemi Linux per la gestione e il monitoraggio degli array RAID (*Redundant Array of Indipendent Disks*). Essa facilità la creazione, la gestione e il monitoraggio di questi array in modo robusto, rendendolo uno strumento essenziale per i sistemi in cui l'integrità e la velocità dei dati sono fondamentali. 

## Creazione di un array
Dipende dal tipo di raid che si vuole configurare ma il comando generale è : 

```bash
sudo mdadm --create /dev/md/MyRAID --level raid_level --raid-devices number_of_disks /dev/sdXN
```

La creazione di un array RAID è un passo fondamentale quando si imposta un sistema in cui è richiesta la ridondanza dei dati o prestazioni migliorate. Questo comando inizializza un nuovo array RAID con livello RAID specificato e dispositivi.
La spiegazione :
- `sudo`: Esegue il comando con privilegi amministrativi, necessario per la modifica delle configurazioni del disco.
- `mdadm`: Lo strumento utilizzato per la gestione del RAID.
- `--create`: Specifica che verrà creato un nuovo array RAID.
- `/dev/md/MyRAID`: Designa il nome del dispositivo RAID creato.
- Determina `--level raid_level`il livello RAID, come RAID 0, 1, 5, ecc., Definendo il comportamento dell'array.
- `--raid-devices number_of_disks`: Indica il numero di dispositivi da includere nell'array RAID.
- `/dev/sdXN`: Rappresenta i dispositivi da utilizzare nell'array (ad es. `/dev/sda1`- Sì, `/dev/sdb1`)

## Fermare un RAID

```bash
sudo mdadm --stop /dev/md0
```

L'interruzione di un array RAID è fondamentale quando bisogna eseguire una manutenzione, test o aggiornamenti sul sistema, senza rischiare l'integrità dei dati. È anche un passaggio richiesto quando bisogna modificare il RAID esistente. 
La spiegazione :
- `sudo`: Concessione dei permessi amministrativi necessari.
- `mdadm`: Invoca lo strumento di gestione RAID.
- `--stop`: Comande il sistema per arrestare il dispositivo RAID specificato.
- `/dev/md0`: Identifica l'array RAID specifico da arrestare.

## Contrassegnare un disco come fallito 

```bash
mdam --fail /dev/md0 /dev/sdX
```

Quando si sospetti che un disco non funzioni bene o fallisca, la marcatura aiuta a impedire la diffusione di dati danneggiati in tutto l'array. Questa operazione notifica al sistema di arrestare l'utilizzo del disco sospetto e consente al RAID di gestire l'errore del disco secondo la sua configurazione.
La spiegazione :
- `sudo`: Assicura che il comando venga eseguito con autorizzazioni appropriate.
- `mdadm`: L'utilità di gestione RAID.
- `--fail`: Contrassegna il disco specificato come guasto nel contesto dell'array RAID.
- `/dev/md0`: Punti all'array RAID contenente il disco contrassegnato come non riuscito.
- `/dev/sdXN`: Specifica il disco preciso (ad es. `/dev/sdc1`) Questo è considerato fallito.

## Rimuovere un disco

```bash
sudo mdadm --remove /dev/md0 /dev/sdX
```

La rimozioni di un disco da un RAID è necessario dopo che è stato contrassegnato come fallito o quando viene eseguito un aggiornamento o una sostituzione. Ciò consente la rimozioni o la sostituzione fisica senza influire sulla funzionalità di altri componenti.
La spiegazione :
- `sudo`Esegue il comando con privilegi di root.
- `mdadm`: Lo strumento di configurazione RAID in uso.
- `--remove`: Dirige il sistema per estrarre il disco specificato dall'array RAID.
- `/dev/md0`: Specifica l'array RAID da cui deve essere rimosso il disco.
- Identifica `/dev/sdXN`il disco previsto per la rimozione (come `/dev/sdd1`)

## Mostrare informazione RAID

```bash
sudo mdadm --detail /dev/md0
```

Controllare lo stato o i dettagli di RAID è fondamentale per il monitoraggio della sua salute e delle sue prestazioni. Questo comando fornisce informazioni complete sul RAID, utili per la diagnosi di problemi, la verifica delle configurazioni e la manutenzione dei record di sistema.
La spiegazione :
- `sudo`: Fornisce le autorizzazioni necessarie per accedere alle informazioni dettagliate sul sistema.
- `mdadm`: Strumento di gestione RAID di riga di comando.
- `--detail`: Genera un rapporto dettagliato dello stato dell'array RAID.
- `/dev/md0`: Identifica quali dati dell'array RAID devono essere visualizzati.
## References

- [[RAID - cos'è, a cosa serve e come funziona]]
- [[Configurazione livello RAID 0 con mdadm]]
- [[Configurazione livello RAID 1 con mdadm]]
- [[Configurazione livello RAID 5 con mdadm]]
- [[Configurazione livello RAID 6 con mdadm]]
- [[[[Configurazione livello RAID 10 con mdadm]]]]
- [[mdadm - aggiungere un disco per aumentare la capienza]]
- [[mdadm - rimuovere e aggiungere un nuovo disco per sostituire un disco guasto]]