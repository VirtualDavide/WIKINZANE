2025-01-09 21:36

Tags : [[DailyLinux]]
# Apache server

### Cosa è Apache Server?

Apache HTTP Server è un software open source per il protocollo HyperText Transfer Protocol (HTTP). È utile per servire pagine Web, immagini, file e altre risorse sulla rete.
### Comandi principali di Apache

Ecco alcuni comandi utili per gestire Apache:

*Avvio di Apache2*
```bash
sudo systemctl start apache2
```

*Arresto di Apache2*
```bash
sudo systemctl stop apache2
```

*Ricarica di Apache2 (per eventuali modifiche al file di configurazione)*
```bash
sudo systemctl restart apache2
```

*Attivazione automatica di Apache2 al boot del sistema*
```bash
sudo systemctl enable apache2
```

*Disattivazione di Apache2 al boot del sistema*
```bash
sudo systemctl disable apache2
```

### Installazione e Rimozione

Per installare Apache su un sistema basato su Debian/Ubuntu:

*Installazione*
```bash
sudo apt update
sudo apt install apache2
```

*Rimozione*
```bash
sudo apt remove apache2
```

*Rimozione dei pacchetti non più necessari*
```bash
sudo apt autoremove
```

### Moduli di Apache

Apache funziona come un nucleo leggero con una serie di moduli che possono essere attivati o disattivati per aggiungere funzionalità. Ecco come gestire i moduli:

*Elenco di tutti i moduli disponibili*
```bash
sudo apache2ctl -M
```

*Attivare un modulo*
```bash
sudo a2enmod <nomedelmodulo>
```

*Disattivare un modulo*
```bash
sudo a2dismod <nomedelmodulo>
```

*Ricarica di Apache per applicare le modifiche ai moduli*
```bash
sudo systemctl reload apache2
```

### Attivazione del modulo PHP 

Per attivare il modulo PHP segui i seguenti passaggi : 

*Installa il modulo PHP (ad esempio , per PHP 8.3)*
```bash
sudo apt install libapache2-mod-php8.3
```

*Attivare il modulo PHP*
```bash
sudo a2denmod php8.3
```

*Ricarica di Apache per applicare le modifiche ai moduli*
```bash
sudo systemctl reload apache2
```

### Log di Apache

Apache genera diversi tipi di log che possono essere utili per risolvere problemi:

- **Access log** : Contiene informazioni su ogni richiesta HTTP ricevuta.
    - Percorso: `/var/log/apache2/access.log`
- **Error log** : Contiene errori generati dall'Apache server.
    - Percorso: `/var/log/apache2/error.log`
## References

- [[LAMPP]]
- [[Apache server (file di configurazione)]]