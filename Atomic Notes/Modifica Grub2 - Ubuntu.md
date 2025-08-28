2025-04-21 09:13

Tags : [[Installazione di Linux e Package Management]] / [[102.2]]

# Modifica Grub2 - Ubuntu

### 🧪 Obiettivo

Mostrare il menu di GRUB all'avvio, anche quando è presente un solo sistema operativo (Ubuntu), per accedere a opzioni avanzate, altri kernel o modificare i parametri di avvio.

### 🔧 Passaggi da seguire

1. **Apri il file di configurazione di GRUB**

   Utilizza un editor di testo con permessi di root. Puoi usare `vim`, `nano` o un altro editor a tua scelta. Ecco un esempio con `nano`:

   ```bash
   sudo nano /etc/default/grub
   ```

2. **Modifica le seguenti righe**

   Cerca e modifica (o aggiungi) le seguenti variabili nel file:

   ```bash
   GRUB_TIMEOUT_STYLE=menu
   GRUB_TIMEOUT=10
   ```

   - `GRUB_TIMEOUT_STYLE=menu`: forza la visualizzazione del menu anche se c'è una sola voce.
   - `GRUB_TIMEOUT=10`: mostra il menu per 10 secondi (puoi cambiare il valore a tuo piacimento).

   Se trovi:

   ```bash
   GRUB_TIMEOUT_STYLE=hidden
   ```

   cambialo in `menu`.

   E se `GRUB_TIMEOUT=0` (o non è presente), modificalo per dare tempo all'utente di scegliere.

3. **Salva le modifiche**

   - Con `nano`, premi `Ctrl + O`, poi `Invio` per salvare, e `Ctrl + X` per uscire.
   - Con `vim`, digita `:wq` e premi `Invio`.

4. **Rigenera la configurazione di GRUB**

   Per applicare le modifiche, esegui il seguente comando:

   ```bash
   sudo update-grub
   ```

   Questo comando rigenera il file `/boot/grub/grub.cfg` utilizzando i template e i valori in `/etc/default/grub`.

5. **Riavvia e verifica**

   Esegui il comando:

   ```bash
   sudo reboot
   ```

   Dopo il riavvio, dovresti vedere comparire il menu di GRUB con il conto alla rovescia. Se premi le frecce su/giù, il timer si ferma e puoi navigare nel menu.

--- 

Spero che questa versione sia utile! Se hai bisogno di ulteriori chiarimenti, non esitare a chiedere.
## References

- [[Grub2]]