2025-07-19 15:51

Tags : [[Linux LPI - 101]] [[103.2]]

# Paste, od, pr
### **Paste**

#### Funzione
Il comando `paste` è utilizzato per unire file di testo riga per riga, creando un output che combina le righe di più file in colonne.

#### Utilizzo
- **Unione di file:**
  ```bash
  paste file1.txt file2.txt
  ```
  Questo comando unisce le righe di `file1.txt` e `file2.txt`, creando un output in cui la prima riga di `file1.txt` è affiancata alla prima riga di `file2.txt`, e così via.

- **Separatore di colonne:**
  ```bash
  paste -d ',' file1.txt file2.txt
  ```
  L'opzione `-d` specifica un delimitatore personalizzato (in questo caso, una virgola) per separare le colonne. Se non viene specificato, il delimitatore predefinito è una tabulazione.

- **Specificare il numero di colonne:**
  ```bash
  paste - - - < file.txt
  ```
  Qui, il comando `-` indica che `paste` deve leggere l'input da `stdin`. Questo comando crea tre colonne dall'input fornito.
#### Situazioni d'uso
- Creare report o tabelle combinando dati da più file.
- Preparare dati per l'analisi, unendo informazioni correlate.
- Formattare output per una migliore leggibilità.
###  **Od**

#### Funzione
Il comando `od` (octal dump) è utilizzato per visualizzare il contenuto di un file in vari formati, come ottale, esadecimale, decimale e ASCII.

#### Utilizzo
- **Visualizzazione in formato ottale:**
  ```bash
  od file.txt
  ```
  Questo comando mostra il contenuto di `file.txt` in formato ottale, con l'offset (indice) a sinistra.

- **Visualizzazione in formato esadecimale:**
  ```bash
  od -x file.txt
  ```
  L'opzione `-x` visualizza il contenuto in formato esadecimale. Questo è utile per analizzare file binari o per il debug.

- **Visualizzazione in formato ASCII:**
  ```bash
  od -c file.txt
  ```
  L'opzione `-c` mostra il contenuto del file in formato ASCII, rendendo più facile la lettura di caratteri e simboli.

- **Visualizzazione con più formati:**
  ```bash
  od -A n -t x1 -t c file.txt
  ```
  Qui, `-A n` disabilita la visualizzazione degli offset, mentre `-t x1` e `-t c` mostrano il contenuto in esadecimale e ASCII, rispettivamente.

#### Situazioni d'uso
- Analizzare file binari o eseguibili.
- Debug di file di testo per identificare caratteri non visibili.
- Verificare il contenuto di file in formati specifici.

### **Pr**

#### Funzione
Il comando `pr` è utilizzato per formattare file di testo per la stampa, creando pagine con intestazioni e numerazione.

#### Utilizzo
- **Formattazione di un file:**
  ```bash
  pr file.txt
  ```
  Questo comando formatta `file.txt` per la stampa, aggiungendo intestazioni con il nome del file e la data.

- **Specificare il numero di colonne:**
  ```bash
  pr -c 2 file.txt
  ```
  L'opzione `-c` specifica il numero di colonne da utilizzare. In questo caso, il file verrà stampato in due colonne.

- **Aggiungere intestazioni personalizzate:**
  ```bash
  pr -h "Intestazione Personalizzata" file.txt
  ```
  L'opzione `-h` consente di specificare un'intestazione personalizzata per il file.

- **Impostare la larghezza delle colonne:**
  ```bash
  pr -w 80 file.txt
  ```
  L'opzione `-w` consente di impostare la larghezza delle colonne in caratteri. Questo è utile per adattare il contenuto a formati di stampa specifici.

#### Situazioni d'uso
- Preparare documenti per la stampa.
## References

- 