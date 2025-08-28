2025-04-26 11:05

Tags : [[Comandi GNU e Unix]] / [[103.1]] / [[DailyLinux]]

# Quoting in bash

Il quoting è necessario per evitare che la shell interpreti erroneamente gli spazi e i caratteri speciali. Ad esempio, se si desidera creare una cartella chiamata "dichiarazione dei redditi", senza quoting, la shell interpreterà gli spazi come separatori di argomenti, creando invece tre cartelle separate.

### Metodi di Quoting

1. **Backslash (`\`)**:
   Utilizzando il carattere backslash prima di uno spazio, si può indicare alla shell di trattare lo spazio come parte del nome della cartella.
   ```bash
   mkdir dichiarazione\ dei\ redditi
   ```

2. **Apici Singoli (`'`)**:
   Racchiudere il nome tra apici singoli impedisce alla shell di interpretare qualsiasi carattere speciale all'interno degli apici.
   ```bash
   mkdir 'dichiarazione dei redditi'
   ```

3. **Doppi Apici (`"`)**:
   I doppi apici consentono di espandere variabili e comandi all'interno della stringa, ma proteggono altri caratteri speciali. Ad esempio, se si desidera stampare il nome utente:
   ```bash
   echo "$USER"
   ```
   Tuttavia, se si desidera stampare il simbolo `$` senza espanderlo, si deve utilizzare il backslash:
   ```bash
   echo "Morro mi deve 5\$"
   ```

### Esempi Pratici
- **Creazione di una Cartella**:
  Per creare una cartella con spazi nel nome:
  ```bash
  mkdir 'dichiarazione dei redditi'
  ```

- **Rimozione di una Cartella**:
  Per rimuovere la cartella creata:
  ```bash
  rmdir 'dichiarazione dei redditi'
  ```

- **Espansione di Variabili**:
  Per stampare il nome dell'utente:
  ```bash
  echo "$USER"
  ```

- **Redirezione**:
  Se si desidera redirigere l'output di un comando in un file, è importante notare che l'operatore di redirezione (`>`) non viene interpretato all'interno dei doppi apici:
  ```bash
  echo "La shell è: $SHELL" > shell.txt
  ```

## References

- 