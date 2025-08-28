2025-01-05 15:22

Tags : [[Architettura del sistema]] / [[101.3]]

# ACPI

ACPI è un demone per gestire gli eventi **ACPI**, come il tasto di accensione, la connessione di una periferica al jack, disconnessione della rete elettrica da un computer portatile e così via. In molte distribuzione comunque il produttore di queste potrebbe già aver inserito regole ben definite per la generazione di questo tipo di eventi, ragion per cui, nella maggioranza dei casi, tale servizio non è attivo. 

Per gestire in autonomia questi eventi non ci basta far altro che creare il file ACPI e specificargli (*bash*) i comportamenti che la macchina deve avere in base agli eventi.

*comando per la creazione del file acpi
```bash
sudo nano /etc/acpi/handler.sh
```

nel file poi scriviamo gli script di nostro interesse.
## References

- [[Dispositivi in Linux]]