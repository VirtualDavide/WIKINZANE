2025-04-22 11:51

Tags : [[Comandi GNU e Unix]] / [[103.1]] / [[DailyLinux]]

# Cambiare shell

La shell è l'interfaccia principale con cui interagisci con il sistema operativo Linux. Permette di eseguire comandi e gestire il sistema. La shell predefinita è la shell che viene avviata automaticamente ogni volta che apri un nuovo terminale.  Cambiare la shell predefinita ti permette di personalizzare l'ambiente di lavoro. Ecco come fare:

**1. Cosa è la Shell?**

La shell è un interprete di comandi che traduce i tuoi comandi in istruzioni comprensibili al sistema operativo. Esempi comuni includono Bash, Korn Shell (ksh) e Zsh.

**2. Comandi Principali**

*   **`chsh` (Change Shell):** Il comando fondamentale per cambiare la tua shell predefinita.
*   **`echo $SHELL`:** Visualizza la shell predefinita attualmente in uso.
*   **`cat /etc/shells`:** Elenca tutte le shell disponibili sul sistema.

**3. Cambiare la Shell Predefinita per l'Utente Corrente**

*   **Sintassi:** `chsh -s /percorso/della/nuova/shell`
*   **Esempio:** `chsh -s /bin/bash` (cambia la shell predefinita a Bash)
*   **Procedura:**
    1.  Apri un terminale.
    2.  Digita il comando `chsh -s /percorso/della/nuova/shell` (sostituendo `/percorso/della/nuova/shell` con il percorso del file eseguibile della shell desiderata, ad esempio `/bin/zsh`).
    3.  Premi Invio.
    4.  Ti verrà richiesta la tua password utente. Inseriscila e premi Invio.
    5.  Dopo aver inserito la password, il comando `chsh` aggiornerà la tua shell predefinita.
    6.  Per verificare la modifica, apri una nuova finestra del terminale e digita `echo $SHELL`. Dovrebbe mostrare il percorso della shell che hai scelto.

**4. Cambiare la Shell Predefinita per un Altro Utente (Richiede Privilegi di Root)**

*   **Sintassi:** `sudo chsh -s /percorso/della/nuova/shell username`
*   **Esempio:** `sudo chsh -s /bin/zsh altroutente`
*   **Procedura:**
    1.  Apri un terminale.
    2.  Digita il comando `sudo chsh -s /percorso/della/nuova/shell username` (sostituendo `/percorso/della/nuova/shell` con il percorso della shell e `username` con il nome dell'utente di cui vuoi cambiare la shell).
    3.  Premi Invio.
    4.  Ti verrà richiesta la password dell'utente root. Inseriscila e premi Invio.
    5.  Dopo aver inserito la password, il comando `chsh` aggiornerà la shell predefinita per l'utente specificato.

**Codice da Copiare e Incollare**

**Comandi per l'utente corrente:**

```bash
# Cambia la shell predefinita a Bash
chsh -s /bin/bash

# Cambia la shell predefinita a Zsh
chsh -s /bin/zsh
```

**Comandi per cambiare la shell di un altro utente (richiede privilegi di root):**

```bash
# Cambia la shell predefinita per l'utente "altroutente" a Zsh
sudo chsh -s /bin/zsh altroutente
```

**Comandi di verifica:**

```bash
# Visualizza la shell predefinita corrente
echo $SHELL
```

**Comando per elencare le shell disponibili:**

```bash
cat /etc/shells
```

**Note Importanti:**

*   Assicurati che il percorso del file eseguibile della shell che stai impostando sia corretto. Puoi trovare il percorso corretto usando il comando `which nome_della_shell`.
*   Dopo aver cambiato la tua shell predefinita, potresti dover chiudere e aprire una nuova finestra del terminale per far prendere effetto le modifiche.

Spero che questa spiegazione completa e i comandi copiabili ti siano d'aiuto! Se hai altre domande, non esitare a chiedere.
## References

- [[Entrare ed uscire dalla shell]]