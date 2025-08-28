clear2025-02-13 21:51

Tags : [[Database]] [[DailyLinux]]

# MySQL - Database e Utenti

## Database
Per accedere al prompt di MySQL dobbiamo digitare il comando : 
```bash
sudo mysql -u root -p
```
Ed inserire la password dell'utente root (*in genere è sempre "root"*).

**Visualizzare i database presenti** : 
```sql
SHOW DATABASES;
```

**Creare un nuovo database** : 
```sql
CREATE DATABASE nome_database;
```

**Selezionare un database per visualizzazione o modifica** : 
```sql
USE <nomedeldatabase>
```

## Utenti
**Creazione di un'utente** : 
```sql
CREATE USER 'nomeUtente'@'inidirizzoIp' IDENTIFIED BY 'password'
```

### Gestione dei Privilegi
In MySQL, puoi concedere vari privilegi a un utente su un database o su tabelle specifiche. Ecco un elenco dei privilegi più comuni che puoi assegnare:
 
 **Privilegi di Accesso e Controllo**
1. **ALL PRIVILEGES**: Concede tutti i privilegi disponibili.
2. **SELECT**: Permette di leggere i dati da una tabella.
3. **INSERT**: Permette di inserire nuovi dati in una tabella.
4. **UPDATE**: Permette di modificare i dati esistenti in una tabella.
5. **DELETE**: Permette di eliminare dati da una tabella.
6. **CREATE**: Permette di creare nuove tabelle o database.
7. **DROP**: Permette di eliminare tabelle o database.
8. **INDEX**: Permette di creare e rimuovere indici su una tabella.
9. **ALTER**: Permette di modificare la struttura di una tabella (ad esempio, aggiungere o rimuovere colonne).
10. **GRANT OPTION**: Permette di concedere i privilegi che l'utente ha ad altri utenti.

**Privilegi Amministrativi**
1. **CREATE USER**: Permette di creare nuovi utenti.
2. **DROP USER**: Permette di eliminare utenti.
3. **RELOAD**: Permette di ricaricare i privilegi e le configurazioni.
4. **SHUTDOWN**: Permette di arrestare il server MySQL.
5. **PROCESS**: Permette di visualizzare i processi in esecuzione.

**Privilegi di Sicurezza**
1. **FILE**: Permette di leggere e scrivere file sul server.
2. **SUPER**: Permette di eseguire operazioni che richiedono privilegi elevati, come terminare processi di altri utenti.

*Esempi*
```sql
GRANT ALL PRIVILEGES ON nomedatabase.* TO 'utente'@'indirizzoIP'
```

```sql
GRANT SELECT, INSERT ON nomedatabase.* TO 'utente'@'indirizzoIP'
```
## References

- [[MySQL]]