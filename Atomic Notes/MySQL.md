2025-02-13 21:45

Tags : [[Database]] [[DailyLinux]]

# MySQL

MySQL è un sistema di gestione di database relazionali (RDBMS) che utilizza il linguaggio SQL (Structured Query Language) per gestire e manipolare i dati. È ampiamente utilizzato per applicazioni web e per la gestione di dati in vari contesti.

## Installazione di MySQL su Linux
Per installare MySQL su una distribuzione Linux, puoi seguire questi passaggi generali. Le istruzioni possono variare leggermente a seconda della distribuzione (ad esempio, Ubuntu, CentOS, etc.).

#### Su Ubuntu/Debian:
```bash
sudo apt install mysql-server
```

**Configura MySQL** : 
```bash
sudo mysql_secure_installation
```

**Avvia il servizio** : 
```bash
sudo systemctl start mysql
```

**Abilita il servizio** : 
```bash
sudo systemctl enable mysql
```


## Rimozione di MySQL su Linux
Per rimuovere MySQL, puoi utilizzare i seguenti comandi:
#### Su Ubuntu/Debian:
```bash
sudo apt remove --purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-*
sudo apt autoremove
sudo apt autoclean
```
## References

- [[Relazioni ed Integrità referenziale]]
- [[Modello Relazionale]]
- [[MySQL - Database e Utenti]]