2025-04-20 21:06

Tags : [[DailyLinux]]

# Struttura file system Linux

### 📂 1. Radice del file system: `/`

Tutto parte dalla directory radice, `/`, da cui si dirama tutta la struttura gerarchica del sistema. Ogni file e directory è contenuto in essa, direttamente o indirettamente.

---

### ⚙️ 2. `/etc` – File di configurazione

- Contiene tutti i file di configurazione di sistema e dei servizi.
    
- Esempi:
    
    - `/etc/ssh/sshd_config`: configurazione del server SSH.
        
    - `/etc/fstab`: partizioni da montare all'avvio.
        
- Modificarla richiede privilegi e attenzione.
    

---

### 📈 3. `/var` – File variabili

- Usata per contenuti che cambiano dinamicamente.
    
- Contiene:
    
    - `/var/log`: log di sistema e servizi (es. `syslog`, `auth.log`, `apache2`).
        
    - `/var/spool`: code (stampa, posta).
        
    - `/var/lib`: dati permanenti usati dai demoni e pacchetti.
        

---

### 🧠 4. `/boot` – Avvio del sistema

- Contiene tutto ciò che serve per avviare il sistema:
    
    - Il kernel (`vmlinuz`)
        
    - L’immagine RAM iniziale (`initrd.img`)
        
    - Il bootloader (`grub`)
        
- Spesso ha una partizione separata.
    

---

### 🧮 5. `/proc` e `/sys` – File system virtuali

- `/proc`:
    
    - Interfaccia tra kernel e utente.
        
    - Contiene info su processi (`/proc/[pid]`) e hardware (`/proc/cpuinfo`, `/proc/meminfo`).
        
- `/sys`:
    
    - Interfaccia per kernel e hardware.
        
    - Usata da udev e altri strumenti per rilevare dispositivi.
        

---

### 🛠️ 6. `/usr` – Unix System Resources

- Contiene risorse di sistema:
    
    - `/usr/bin`: programmi per utenti.
        
    - `/usr/sbin`: programmi per amministratori.
        
    - `/usr/lib`: librerie.
        
    - `/usr/share`: documentazione, icone, dati condivisi.
        

---

### 🏠 7. `/home` – Directory utente

- Ogni utente ha la propria cartella, ad esempio `/home/mario`.
    
- Contiene file personali, documenti e configurazioni.
    

---

### 👑 8. `/root` – Home dell’utente root

- Separata da `/home`.
    
- È la home directory dell'amministratore del sistema.
    

---

### 🔧 9. `/bin` e `/sbin` – Comandi essenziali

- `/bin`: comandi base accessibili a tutti (es. `ls`, `cp`, `mv`).
    
- `/sbin`: strumenti di amministrazione, usati da root (es. `fsck`, `reboot`).
    
- Oggi alcune distro li spostano dentro `/usr`.
    

---

### 🧱 10. `/lib` e `/lib64` – Librerie condivise

- Contengono le librerie necessarie all’avvio del sistema.
    
- Supportano i binari presenti in `/bin` e `/sbin`.
    

---

### 💽 11. `/dev` – Dispositivi

- Rappresenta i dispositivi hardware come file.
    
- Esempi:
    
    - `/dev/sda`: disco rigido.
        
    - `/dev/tty0`: terminale virtuale.
        

---

### 🧹 12. `/tmp` – File temporanei

- Usata per file temporanei.
    
- Pulita ad ogni riavvio.
    

---

### 💿 13. `/media` e `/mnt` – Montaggi

- `/media`: per dispositivi rimovibili (chiavette USB, CD).
    
- `/mnt`: per montaggi manuali o temporanei, gestiti dall’amministratore.
## References

- [[Progettare il partizionamento dei dischi]]