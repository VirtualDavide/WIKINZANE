2025-03-26 18:18

Tags : [[PHP]] [[ServerSideDevelopment]]

# Connessione Database - PHP

#### 1. **Prerequisiti**
   - Assicurati di avere un server web (come Apache o Nginx) e PHP installati.
   - Un server di database MySQL o MariaDB deve essere in esecuzione.
   - Conoscenza delle credenziali di accesso al database (nome utente, password, nome del database).

#### 2. **Estensione MySQLi**
   - Utilizza l'estensione MySQLi (MySQL Improved) per interagire con il database. MySQLi supporta le query preparate, che offrono maggiore sicurezza contro le iniezioni SQL.
#### 3. **Connessione al Database**
   - Utilizza la classe `mysqli` per stabilire una connessione al database.
   ```php
   $conn = new mysqli($servername, $username, $password, $dbname);
   ```

   - Controlla se la connessione è avvenuta con successo:
   ```php
   if ($conn->connect_error) {
       die("Connessione fallita: " . $conn->connect_error);
   }
   ```

#### 4. **Esecuzione di Query**
   - **Query Preparata**: Utilizza le query preparate per eseguire operazioni di `INSERT`, `UPDATE`, `DELETE` e `SELECT`.
   - Prepara la query:
   ```php
   $stmt = $conn->prepare("INSERT INTO utenti (nome, email) VALUES (?, ?)");
   ```

   - **Binding dei Parametri**: Usa `bind_param()` per legare le variabili ai segnaposto nella query. Specifica il tipo di dato:
   - `s` - Stringa
   - `i` - Intero
   - `d` - Double
   - `b` - Blob
   ```php
   $stmt->bind_param("ss", $nome, $email); // Esempio per stringhe
   ```

   - **Esecuzione della Query**: Esegui la query con `execute()`.
   ```php
   $stmt->execute();
   ```

#### 5. **Gestione dei Risultati**
   - Per le query `SELECT`, utilizza `get_result()` per ottenere i dati:
   ```php
   $result = $stmt->get_result();
   ```

   - Controlla il numero di righe restituite e itera attraverso i risultati:
   ```php
   if ($result->num_rows > 0) {
       while ($row = $result->fetch_assoc()) {
           echo "Nome: " . $row['nome'] . " - Email: " . $row['email'];
       }
   }
   ```

   - Per `INSERT`, `UPDATE` e `DELETE`, controlla il risultato dell'esecuzione:
   ```php
   if ($stmt->execute()) {
       echo "Operazione completata con successo.";
   } else {
       echo "Errore: " . $stmt->error;
   }
   ```

#### 6. **Chiusura della Connessione**
   - Chiudi la dichiarazione e la connessione al database dopo aver completato le operazioni:
   ```php
   $stmt->close();
   $conn->close();
   ```

#### 7. **Sicurezza**
   - Utilizza sempre query preparate per prevenire le iniezioni SQL.
   - Valida e sanifica i dati in ingresso prima di utilizzarli nelle query.

#### 8. **Esempio Completo**
   Ecco un esempio completo di connessione e operazione di inserimento:
   ```php
   $servername = "localhost";
   $username = "tuo_utente";
   $password = "tua_password";
   $dbname = "esempio_db";

   $conn = new mysqli($servername, $username, $password, $dbname);

   if ($conn->connect_error) {
       die("Connessione fallita: " . $conn->connect_error);
   }

   $stmt = $conn->prepare("INSERT INTO utenti (nome, email) VALUES (?, ?)");
   $stmt->bind_param("ss", $nome, $email);

   $nome = "Mario Rossi";
   $email = "mario@example.com";

   if ($stmt->execute()) {
       echo "Dati inseriti con successo!";
   } else {
       echo "Errore nell'inserimento: " . $stmt->error;
   }

   $stmt->close();
   $conn->close();
   ```

### Conclusione
Questa guida fornisce una panoramica completa
## References

- [[Strutture Dati php]]
- [[Programmazione Orientata agli Oggetti in PHP]]