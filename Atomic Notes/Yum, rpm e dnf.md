2025-04-21 11:11

Tags : [[Installazione di Linux e Package Management]] / [[102.5]]

# Yum, rpm e dnf

### Gestione dei pacchetti RPM e Yum/DNF su distribuzioni come RedHat, CentOS e Fedora

Le distribuzioni Linux come RedHat, CentOS e Fedora utilizzano il sistema di gestione dei pacchetti RPM (Red Hat Package Manager) e i gestori di pacchetti Yum (Yellowdog Updater, Modified) e DNF (Dandified YUM) per installare, aggiornare e rimuovere software. Ecco una panoramica su come utilizzare questi strumenti.

#### Installazione di un pacchetto RPM

1. **Scaricare il pacchetto RPM**: Prima di tutto, scarica il pacchetto RPM desiderato, ad esempio `Nautilus-Dropbox.rpm`.

2. **Visualizzare informazioni sul pacchetto**:
   ```bash
   rpm -qpi Nautilus-Dropbox.rpm
   ```
   Questo comando mostra informazioni sul pacchetto, come la versione, l'architettura e le dipendenze.

3. **Elencare i file contenuti nel pacchetto**:
   ```bash
   rpm -qpl Nautilus-Dropbox.rpm
   ```
   Questo comando elenca i file che verranno installati dal pacchetto.

4. **Installare il pacchetto**:
   ```bash
   sudo rpm -ivh Nautilus-Dropbox.rpm
   ```
   L'opzione `-i` indica l'installazione, `-v` fornisce output verboso e `-h` mostra una barra di progresso.

5. **Gestire le dipendenze**: Se ci sono dipendenze non soddisfatte, puoi utilizzare Yum o DNF per installarle automaticamente.

6. **Visualizzare i pacchetti installati**:
   ```bash
   rpm -qa
   ```

7. **Visualizzare informazioni su un pacchetto installato**:
   ```bash
   rpm -qi <nome_pacchetto>
   ```

8. **Elencare i file installati da un pacchetto**:
   ```bash
   rpm -ql <nome_pacchetto>
   ```

9. **Verificare a quale pacchetto appartiene un file**:
   ```bash
   rpm -qf <percorso_file>
   ```

10. **Estrarre i file da un pacchetto RPM**:
    ```bash
    rpm2cpio Nautilus-Dropbox.rpm | cpio -idmv
    ```

#### Utilizzo di Yum/DNF

1. **Aggiornare i repository**:
   ```bash
   sudo yum update
   ```
   o
   ```bash
   sudo dnf update
   ```
   Questo comando aggiorna l'elenco dei pacchetti disponibili dai repository.

2. **Cercare un pacchetto**:
   ```bash
   yum search <nome_pacchetto>
   ```
   o
   ```bash
   dnf search <nome_pacchetto>
   ```

3. **Visualizzare informazioni su un pacchetto**:
   ```bash
   yum info <nome_pacchetto>
   ```
   o
   ```bash
   dnf info <nome_pacchetto>
   ```

4. **Installare un pacchetto**:
   ```bash
   sudo yum install <nome_pacchetto>
   ```
   o
   ```bash
   sudo dnf install <nome_pacchetto>
   ```

5. **Rimuovere un pacchetto**:
   ```bash
   sudo yum remove <nome_pacchetto>
   ```
   o
   ```bash
   sudo dnf remove <nome_pacchetto>
   ```

6. **Rimuovere un pacchetto e le sue dipendenze non più necessarie**:
   ```bash
   sudo yum autoremove
   ```
   o
   ```bash
   sudo dnf autoremove
   ```

7. **Installazione di un gruppo di pacchetti**:
   ```bash
   sudo yum groupinstall "<nome_gruppo>"
   ```
   o
   ```bash
   sudo dnf groupinstall "<nome_gruppo>"
   ```

8. **Visualizzare i gruppi di pacchetti disponibili**:
   ```bash
   yum group list
   ```
   o
   ```bash
   dnf group list
   ```

9. **Controllare quali pacchetti forniscono un file specifico**:
    ```bash
    yum provides <percorso_file>
    ```
    o
    ```bash
    dnf provides <percorso_file>
    ```

### Conclusione

In sintesi, RPM, Yum e DNF sono strumenti fondamentali per la gestione dei pacchetti nelle distribuzioni basate su RedHat. 

- **RPM** è utilizzato per gestire i pacchetti individuali, consentendo di installare, rimuovere e interrogare i pacchetti direttamente.
- **Yum** e **DNF** semplificano l'installazione e la gestione delle dipendenze, rendendo più facile mantenere il sistema aggiornato e funzionante. DNF è il successore di Yum e offre miglioramenti in termini di prestazioni e funzionalità, ma la sintassi è molto simile, quindi gli utenti di Yum troveranno facile passare a DNF.

Utilizzando questi strumenti, puoi facilmente installare, aggiornare e rimuovere software sul tuo sistema Linux, gestendo anche le dipendenze necessarie per garantire che tutto funzioni correttamente. Se hai bisogno di ulteriori dettagli o chiarimenti su uno specifico comando o funzionalità, non esitare a chiedere!
## References

- [[Zipper]]