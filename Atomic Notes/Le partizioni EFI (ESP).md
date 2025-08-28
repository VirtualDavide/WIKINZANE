2025-04-20 22:13

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]]

# Le partizioni EFI (ESP)

Nel contesto moderno dell'avvio dei sistemi, **UEFI (Unified Extensible Firmware Interface)** ha ormai sostituito il vecchio standard **MBR (Master Boot Record)**. A differenza di MBR, UEFI utilizza una propria modalità di avvio che prevede l'esistenza di una partizione specifica chiamata **EFI System Partition (ESP)**, formattata tipicamente in **FAT32**. Questa partizione contiene file eseguibili UEFI, ossia i **bootloader** dei sistemi operativi installati.

Durante il processo di boot, il firmware UEFI cerca questa partizione, la monta, e da lì esegue uno degli eseguibili presenti (come GRUB o bootmgfw.efi per Windows). L’eseguibile scelto si occupa poi di caricare il kernel del sistema operativo.

Per esplorare in pratica la configurazione, è utile iniziare osservando le partizioni presenti:

```bash
parted -l
```

Nel caso di una macchina con UEFI attivo, tra le varie partizioni dovrebbe essere visibile una FAT32 con i flag `boot` e `esp` abilitati. Questo indica chiaramente che si tratta della **partizione EFI**.

Una volta che il sistema operativo è avviato, è possibile esplorare il contenuto della partizione EFI. Tipicamente, viene montata in `/boot/efi`. È possibile verificare le mount attive con:

```bash
mount | grep /boot
```

Navigando all’interno della directory EFI si nota la struttura gerarchica standard, con una directory principale chiamata `EFI` e, al suo interno, sottodirectory per ciascun sistema operativo installato.

Per analizzare il tipo di file e confermare che si tratta di un eseguibile UEFI:

```bash
file /boot/efi/EFI/GRUB/grubx64.efi
```

Durante l’installazione di un sistema operativo su una macchina con firmware UEFI, viene tipicamente creata (o utilizzata) questa partizione EFI, dove il bootloader del sistema viene copiato nella directory corrispondente. Questa organizzazione permette il **dual boot** o **multi-boot**, mantenendo separati i bootloader dei vari sistemi.
## References

- [[EFI-UEFI]]
- [[Boot loader Linux]]