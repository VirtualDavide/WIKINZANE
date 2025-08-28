2025-03-23 22:10

Tags : [[Docker]]

# Eseguire un Container


1. **Scaricare l'Immagine di Ubuntu**:
   - Utilizza il comando `docker pull` per scaricare l'ultima immagine disponibile di Ubuntu.
   ```bash
   docker pull ubuntu
   ```

2. **Eseguire un Container Ubuntu**:
   - Quando esegui `docker run ubuntu`, il container termina immediatamente perché non c'è un comando da eseguire (*Ubuntu è un'immagine base senza un servizio in esecuzione*).
   ```bash
   docker run ubuntu
   ```

3. **Eseguire la Shell Bash nel Container**:
   - Per avviare un container Ubuntu e accedere alla shell bash, utilizza il comando:
   ```bash
   docker run -it ubuntu bash
   ```
   - L'opzione `-it` combina `-i` (interactive) e `-t` (terminal), collegando il terminale corrente alla shell bash del container.

4. **Interazione con il Container**:
   - Una volta dentro il container, puoi eseguire comandi come `apt update` o altri comandi di Ubuntu.
   - Per uscire dalla shell bash, puoi usare `exit` o premere `Ctrl + D`, il che terminerà il container.

5. **Mantenere il Container in Esecuzione**:
   - Se desideri uscire dalla shell senza terminare il container, puoi usare `Ctrl + P` seguito da `Ctrl + Q`. Questo ti riporta al terminale host, ma il container rimane in esecuzione.

6. **Riattaccarsi a un Container in Esecuzione**:
   - Puoi riattaccarti a un container in esecuzione utilizzando il comando `docker attach` seguito dall'ID del container.
   ```bash
   docker attach <container_id>
   ```

7. **Creare un Container con un Nome Specifico**:
   - Puoi assegnare un nome a un container al momento della creazione utilizzando l'opzione `--name`:
   ```bash
   docker run -it --name prova-ubuntu ubuntu bash
   ```

### Conclusione

Questi passaggi e comandi ti permettono di interagire con i container Docker utilizzando l'immagine di Ubuntu. È importante comprendere come avviare un container, interagire con esso e gestirlo correttamente. Nella prossima lezione, esplorerai ulteriormente come gestire i container, fermarli, riavviarli e altro ancora. Se hai ulteriori domande o hai bisogno di chiarimenti, non esitare a chiedere!
## References

- [[Cercare,scaricare ed eseguire un'immagine]]