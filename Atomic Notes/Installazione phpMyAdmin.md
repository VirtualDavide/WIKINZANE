2025-04-16 22:15

Tags : [[DailyLinux]]

# Installazione phpMyAdmin

Per installare phpMyAdmin su una macchina Ubuntu, puoi seguire questi passaggi:

### 1. Aggiorna il sistema
Prima di tutto, assicurati che il tuo sistema sia aggiornato. Apri il terminale e digita:

```bash
sudo apt update
sudo apt upgrade
```

### 2. Installa il server web e PHP
Se non hai già installato un server web (come Apache) e PHP, puoi farlo con i seguenti comandi:

```bash
sudo apt install apache2
sudo apt install php libapache2-mod-php php-mysql
```

### 3. Installa phpMyAdmin
Ora puoi installare phpMyAdmin. Esegui il seguente comando:

```bash
sudo apt install phpmyadmin
```

Durante l'installazione, ti verrà chiesto di scegliere il server web da configurare. Seleziona `apache2` e premi `Invio`. Ti verrà anche chiesto se desideri utilizzare `dbconfig-common` per configurare il database. Scegli "Sì" e inserisci le credenziali del tuo database MySQL quando richiesto.

### 4. Configura Apache
Dopo l'installazione, devi configurare Apache per riconoscere phpMyAdmin. Puoi farlo creando un file di configurazione:

```bash
echo 'Include /etc/phpmyadmin/apache.conf' | sudo tee -a /etc/apache2/apache2.conf
```

### 5. Riavvia Apache
Per applicare le modifiche, riavvia Apache:

```bash
sudo systemctl restart apache2
```

*provare anche ad eseguire un restart di mysql*
### 6. Accedi a phpMyAdmin
Ora puoi accedere a phpMyAdmin aprendo il tuo browser e navigando all'URL:

```
http://localhost/phpmyadmin
```

Inserisci le credenziali del tuo database MySQL per accedere.

### 7. (Opzionale) Sicurezza
È consigliabile proteggere ulteriormente l'accesso a phpMyAdmin. Puoi farlo impostando una password per l'utente `phpmyadmin` o limitando l'accesso tramite file `.htaccess`.

## References

- [[Apache server]]