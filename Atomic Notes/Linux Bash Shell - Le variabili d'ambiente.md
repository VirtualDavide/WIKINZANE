2025-04-26 09:19

Tags : [[Comandi GNU e Unix]] / [[103.1]] / [[DailyLinux]]

# Linux Bash Shell - Le variabili d'ambiente

### Nota di Spiegazione sui Concetti Esposti nel Video

In questo video, sono stati trattati vari aspetti delle variabili d'ambiente in Bash, un argomento fondamentale per chiunque desideri approfondire l'uso di Linux e la programmazione in shell. Di seguito, troverai un riepilogo dei concetti principali, insieme ai comandi utilizzati e spiegazioni più dettagliate.

#### Cosa Sono le Variabili d'Ambiente

1. **Definizione di Variabile**:
   - Una variabile è un contenitore che memorizza dati. In Bash, le variabili d'ambiente sono utilizzate per configurare il comportamento del sistema e delle applicazioni. Di solito, i nomi delle variabili d'ambiente sono scritti in maiuscolo per distinguerli dalle variabili locali.

2. **Esempi di Variabili d'Ambiente**:
   - Alcuni esempi comuni di variabili d'ambiente includono:
     - `USER`: contiene il nome dell'utente attualmente loggato.
     - `PWD`: indica il percorso della directory corrente.
     - `OLDPWD`: mostra il percorso della directory precedente.

#### Visualizzazione e Utilizzo delle Variabili

3. **Visualizzazione delle Variabili**:
   - Puoi visualizzare il contenuto di una variabile utilizzando il comando `echo`. Ad esempio:
     ```bash
     echo $USER
     ```
     Questo comando stamperà il nome dell'utente attualmente loggato.

4. **Impostazione di Variabili**:
   - Per impostare una nuova variabile, puoi utilizzare la seguente sintassi:
     ```bash
     merenda=torta
     ```
     Questo comando crea una variabile chiamata `merenda` con il valore `torta`. Tuttavia, questa variabile sarà disponibile solo nella sessione corrente della shell.

5. **Verifica della Variabile**:
   - Se provi a visualizzare la variabile `merenda` in un'altra shell, non sarà visibile:
     ```bash
     echo $merenda
     ```
     Questo restituirà un valore vuoto perché la variabile è locale alla sessione in cui è stata creata.

#### Esportazione delle Variabili

6. **Esportazione delle Variabili**:
   - Se desideri che una variabile sia disponibile anche nelle shell figlie, devi "esportarla" utilizzando il comando `export`:
     ```bash
     export merenda
     ```
     Dopo aver esportato la variabile, sarà accessibile in tutte le shell figlie create dalla shell corrente.

7. **Creazione e Esportazione in Unico Passaggio**:
   - Puoi anche creare e esportare una variabile in un unico passaggio:
     ```bash
     export gommista=Gianni
     ```
     In questo modo, la variabile `gommista` sarà immediatamente disponibile in tutte le shell figlie.

#### Visualizzazione dell'Albero delle Shell

8. **Visualizzazione dell'Albero delle Shell**:
   - Per vedere la gerarchia delle shell attive e i loro processi, puoi utilizzare il comando:
     ```bash
     ps --forest
     ```
     Questo comando mostra un albero dei processi, evidenziando le relazioni tra le shell padre e figlie. È utile per comprendere come le varie sessioni di shell sono collegate tra loro.

#### Eliminazione delle Variabili

9. **Eliminazione delle Variabili**:
   - Per rimuovere una variabile, puoi utilizzare il comando `unset`:
     ```bash
     unset merenda
     ```
     Dopo aver eseguito questo comando, la variabile `merenda` non sarà più disponibile.

#### Opzioni di Bash

10. **Visualizzazione delle Opzioni di Bash**:
    - Puoi visualizzare le opzioni attive in Bash utilizzando il comando `set`. Questo comando mostra tutte le variabili e le opzioni correnti della shell.
    - Ad esempio, l'opzione `export` determina se le variabili devono essere automaticamente esportate nelle shell figlie. Puoi attivare o disattivare questa opzione con:
      ```bash
      set -o export
      ```
      o
      ```bash
      set +o export
      ```

## References

- [[Entrare ed uscire dalla shell]]
- [[Cambiare shell]]