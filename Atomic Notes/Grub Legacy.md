2025-04-21 08:44

Tags :  [[Installazione di Linux e Package Management]] / [[102.2]]

# Grub Legacy

## 🔧 **Cos'è GRUB Legacy**

- **GRUB (GRand Unified Bootloader)** è un bootloader usato per avviare sistemi operativi.
- **GRUB Legacy** è la versione 0.9x, precedente all’attuale **GRUB 2**.
- Ancora utile su **vecchie macchine o sistemi legacy**, ad esempio con Ubuntu 8.10.

## 🧱 **Struttura delle Partizioni**

- La **partizione di boot** può essere separata o unita a quella di root.
- Le partizioni possono essere:
    
    - **Primarie**
    - **Estese**
    - **Swap**
        
- Comandi utili per visualizzarle:
    
    - `fdisk -l`
    - `gparted` (se installato)

## 🛠️ **Installazione di GRUB**

- Comando base : `grub-install /dev/sdX`
-  `/dev/sdX` = intero disco (MBR)
- `/dev/sdX1` = singola partizione

## 📄 **File di configurazione: `/boot/grub/menu.lst`**

- Contiene le **voci di boot** e le impostazioni generali:
    - `default`: quale entry avviare (0 = prima)
    - `timeout`: secondi prima dell’avvio automatico
    - `hiddenmenu`: se commentato, il menu viene mostrato
        
- Ogni entry inizia con:

```bash
title Ubuntu
root (hd0,0)
kernel /boot/vmlinuz... root=UUID=... ro quiet splash
initrd /boot/initrd.img...
```

## 🧾 **Modifica delle entry**

- Puoi aggiungere, modificare o rimuovere voci manualmente.
- Parametri interessanti da modificare:
    - `quiet`: disabilita output verboso → rimuovendolo, vedrai i messaggi di boot.
    - `splash`: rimuove il logo grafico.
    - `3`: avvia in modalità **runlevel 3** (multiuser, no GUI).
    - `root=`: può essere in formato `UUID=` o `(hdX,Y)`.

## 💻 **Modalità interattiva (`premi C` al boot)**

- Apre una **shell minimale** di GRUB.
- Permette il boot manuale:
```bash
root (hd0,0)
kernel /boot/vmlinuz... root=/dev/sdX ro
initrd /boot/initrd.img...
boot
```

Utile per **ripristinare GRUB** o fare boot se il file `menu.lst` è rotto.
## References

- [[Grub2]]
- [[Boot loader Linux]]