2025-04-26 08:54

Tags : [[Comandi GNU e Unix]] / [[103.1]] / [[DailyLinux]]

# Entrare ed uscire dalla shell

#### Accesso alle Shell

1. **Apertura del Terminale**:
   - In un ambiente desktop come GNOME, uno dei modi più semplici per aprire un terminale è fare clic con il tasto destro del mouse e selezionare "*Apri nel terminale*". Questo metodo è veloce e non richiede di navigare nei menu.

2. **Terminali Virtuali**:
   - Linux offre la possibilità di accedere a diverse sessioni testuali, note come terminali virtuali (TTY). Puoi passare da una sessione all'altra utilizzando la combinazione di tasti `Ctrl + Alt + F1` fino a `F6`. Ogni TTY ti permette di avere una sessione di terminale separata.
   - La sessione grafica, invece, è generalmente accessibile tramite `Ctrl + Alt + F7`. Questo ti consente di tornare all'ambiente desktop grafico.

#### Login e Visualizzazione dei Processi

3. **Login Testuale**:
   - Una volta che hai selezionato una TTY, puoi effettuare il login inserendo il tuo nome utente e la password. Questo ti porterà a una shell testuale, dove puoi eseguire comandi direttamente.

4. **Visualizzazione dei Processi**:
   - Per vedere quali processi sono attivi, puoi utilizzare il comando `ps`. Questo comando mostra i processi avviati dall'utente corrente. Ad esempio, digitando semplicemente `ps`, otterrai un elenco dei tuoi processi attivi.
   - Se desideri visualizzare i processi di un utente specifico, puoi utilizzare il comando:
     ```bash
     ps -U nomeutente
     ```
     Sostituisci `nomeutente` con il nome dell'utente di cui vuoi vedere i processi. Questo comando ti fornirà un elenco dettagliato dei processi in esecuzione per quell'utente, permettendoti di monitorare le attività di altri utenti sul sistema.

#### Uscita dalle Shell

5. **Comandi per Uscire**:
   - Ci sono diversi modi per uscire da una shell. Il comando più comune è `exit`, che chiude la shell corrente e ti riporta al livello precedente.
   - Un altro comando utile è `logout`, che è specifico per le login shell. Funziona solo se hai effettuato il login tramite `su` (substitute user) e desideri uscire dalla sessione di quel particolare utente.
   - Inoltre, puoi utilizzare la combinazione di tasti `Ctrl + D`, che chiude il terminale in modo simile al comando `exit`.

6. **Esecuzione di Comandi e Logout**:
   - Un aspetto interessante della gestione delle shell è la possibilità di eseguire un comando e chiudere automaticamente la shell al termine dell'esecuzione. Questo può essere fatto utilizzando il comando `exec`. Ad esempio:
     ```bash
     exec ping 8.8.8.8 -c 4
     ```
     In questo caso, il comando `ping` invia quattro pacchetti al server DNS di Google. Una volta completato il ping, la shell si chiude automaticamente. Questo è particolarmente utile in scenari in cui desideri eseguire un comando e non hai bisogno di una shell aperta dopo che il comando è terminato.
## References

- [[Cambiare shell]]
- [[Linux Bash Shell - Le variabili d'ambiente]]