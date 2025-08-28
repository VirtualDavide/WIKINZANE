2024-12-31 14:09

Tags : [[Architettura del sistema]] / [[101.3]]

# Init del SO

Dopo il caricamento del kernel (ed eventualmente del initrd), il processo `/sbin/init` e il primo ad essere avviato. Lo scopo di `init` è far partire tutti gli altri processi, tutti i demoni, e gli altri processi necessari al sistema operativo.

Essendo il primo avrà come PID sempre 1.

Rimane attivo fino allo spegnimento di tutti i processi figli.

### Tipi di Init

- **System V Init**:
    - Tradizionale metodo di inizializzazione.
    - Il processo è chiamato `init`.
- **Upstart**:
    - Un sistema di inizializzazione più moderno.
    - Utilizza il concetto di **jobs** per gestire i processi.
	    - Una job in Upstart è una configurazione che definisce **come e quando avviare, fermare o gestire un processo** o un servizio. Ogni job è descritto in un file di configurazione.
	- il grande vantaggio di Upstart è che a differenza del vecchio systemVinit, può avviare o fermare demoni in base non solo all’entrata in un runlevel, ma anche ad eventi specifici, come l’avvio di un altro servizio, il montaggio di un filesystem o un evento hardware. `initctl show-config`
- **systemd**:
    - Un sistema di inizializzazione avanzato e più recente.
    - Ogni unit rappresenta un singolo oggetto che systemd può gestire, come un servizio, un socket, un dispositivo, un file system, e così via
    - `/sbin/init` è un collegamento a `/lib/systemd/systemd`.
    - Utilizza **units** per definire i processi da eseguire.
        - **Esempi di units**:
            - `.service`: Servizi di sistema.
            - `.socket`: Socket di rete.
            - `.device`: Dispositivi hardware.
            - `.mount`: Montaggio di file system.
            - `.automount`: Montaggio automatico.
            - `.swap`: Spazio di swap.
            - `.target`: Gruppi di unità.
            - `.path`: Monitoraggio di percorsi.
            - `.timer`: Timer per attività programmate.
            - `.snapshot`: Snapshot di unità.
            - `.slice`: Gruppi di processi.
            - `.scope`: Gruppi di processi gestiti.
        **Systemd** sostituisce il concetto di "**runlevel**" con il concetto di "**boot target**". La seguente tabella sintetizza il _boot target_ equivalente per ciascun _runlevel_:
Runlevel:     Target:

0                   poweroff.target

1                   rescue.target

2, 3, 4           multi-user.target

5                   graphical.target

6                   reboot.target

### Ripristino in caso di errore

- Se il kernel si avvia ma non riesce a lanciare `init`, possiamo provare a riparare il sistema.
- **Esempio di comando**: `init=/bin/sh`
    - Questo comando avvia una shell (`sh`) con privilegi di root.
    - Permette di eseguire comandi per tentare di riparare il sistema.
## References

- [[Runlevel]]