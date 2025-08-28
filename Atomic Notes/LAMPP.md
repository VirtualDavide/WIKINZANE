comuqnue 2024-12-12 22:17

Tags : [[DailyLinux]]

# LAMPP

LAMP è un acronimo che sta per:

- **L**inux: il sistema operativo su cui il stack è eseguito.
- **A**pache: il server web che gestisce le richieste HTTP e serve le pagine web.
- **M**ySQL: il sistema di gestione di database relazionali che memorizza i dati delle applicazioni web.
- **P**HP: il linguaggio di programmazione utilizzato per sviluppare applicazioni web dinamiche.

(*XAMPP, d'altra parte, è un pacchetto software che include LAMP, ma con alcune aggiunte e modifiche. La "X" in XAMPP sta per "cross-platform"*)
### Installazione Linux

1. Scaricare l'ultima versione di LAMPP dal sito : https://www.apachefriends.org/download.html
2. Modificare i permessi al file.run :  `chmod +x xampp-linux-x64-7.4.30-0-installer.run
3. Eseguire il file di installazione  : `sudo ./xampp-linux-x64-7.4.30-0-installer.run

### Avvio di LAMPP

Una volta completata l'installazione possiamo avviare LAMPP con il comando : 

```bash
sudo /opt/lampp/lampp start
```
`
Avvio dell'interfaccia Grafica
```bash
sudo /opt/lampp/lampp gui
```

### Avvio server

```bash
sudo /opt/lampp/lampp startapache
```
```bash
sudo /opt/lampp/lampp startftp
```
```bash
sudo /opt/lampp/lampp startmysql
```
### Fermare server

```bash
sudo /opt/lampp/lampp stopapache
```
```bash
sudo /opt/lampp/lampp stopmysql
```
```bash
sudo /opt/lampp/lampp stopftp
```

### Controllare lo stato del server

```bash
sudo /opt/lampp/lampp status
```

### Disinstallare LAMPP 

```bash
sudo rm -rf /opt/lampp
```

P.S *per verificare l'installazione di LAMPP basta che controlliamo se esiste la cartella con il comando `ls /opt/lampp`*

## References

- [[Server]]