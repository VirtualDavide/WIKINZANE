2025-04-26 09:39

Tags : [[Comandi GNU e Unix]] / [[103.1]] / [[DailyLinux]]

# Bash Shell - Alias
#### Cosa Sono gli Alias

1. **Definizione di Alias**:
   - Un alias è una scorciatoia che consente di eseguire un comando con parametri predefiniti senza doverli digitare ogni volta. Gli alias possono semplificare l'uso della shell e rendere più veloce l'esecuzione di comandi frequenti.

2. **Visualizzazione degli Alias Attivi**:
   - Puoi visualizzare gli alias attivi nella sessione corrente digitando:
     ```bash
     alias
     ```
     Questo comando mostrerà un elenco di tutti gli alias definiti, come `ll` per `ls -l` o `la` per `ls -a`.

#### Creazione e Rimozione di Alias

3. **Creazione di un Alias**:
   - Per creare un nuovo alias, utilizza la seguente sintassi:
     ```bash
     alias nome_alias='comando'
     ```
     Ad esempio, per creare un alias `lh` che esegue `ls -lh`, puoi digitare:
     ```bash
     alias lh='ls -lh'
     ```

4. **Rimozione di un Alias**:
   - Se desideri rimuovere un alias, puoi utilizzare il comando `unalias`:
     ```bash
     unalias nome_alias
     ```
     Ad esempio, per rimuovere l'alias `ll`, puoi digitare:
     ```bash
     unalias ll
     ```

#### Comportamento degli Alias

5. **Esecuzione di Comandi Senza Alias**:
   - Se desideri eseguire un comando senza che venga applicato l'alias, puoi utilizzare il carattere di escape `\` (backslash) prima del comando. Ad esempio:
     ```bash
     \ls
     ```
     Questo eseguirà il comando `ls` senza applicare l'alias.

6. **Persistenza degli Alias**:
   - Gli alias creati nella sessione corrente non persistono dopo il logout. Per rendere permanenti gli alias, puoi aggiungerli a un file di configurazione, come `~/.bashrc` o `~/.bash_profile`. Ad esempio, per aggiungere un alias al file `.bashrc`, puoi aprire il file con un editor di testo e aggiungere la riga:
     ```bash
     alias lh='ls -lh'
     ```

#### Opzioni di Bash

8. **Controllo delle Opzioni di Bash**:
   - Puoi visualizzare le opzioni attive in Bash utilizzando il comando `shopt`. Questo comando mostra le opzioni di shell attive, tra cui `expand_aliases`, che determina se gli alias devono essere espansi automaticamente.
   - Per disattivare l'espansione degli alias, puoi utilizzare:
     ```bash
     shopt -u expand_aliases
     ```
     Questo impedirà l'espansione degli alias per la sessione corrente.

9. **Riattivazione delle Opzioni**:
   - Puoi riattivare l'espansione degli alias con:
     ```bash
     shopt -s expand_aliases
     ```

## References

- [[Linux Bash Shell - Le variabili d'ambiente]]