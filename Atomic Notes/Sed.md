2025-07-19 16:27

Tags : [[Linux LPI - 101]] [[103.2]]

# Sed
#### Funzione
`sed` (stream editor) è un potente strumento di editing di flussi di testo in Linux. Viene utilizzato per modificare file di testo in modo non interattivo, permettendo di eseguire operazioni come sostituzioni, eliminazioni e inserimenti di righe.
#### Utilizzo

1. **Stampa di un range di righe**
   - Per stampare un intervallo di righe da un file, puoi utilizzare `sed` in combinazione con l'opzione `-n` per sopprimere l'output predefinito e specificare le righe da stampare.
   ```bash
   sed -n '1,5p' x.conf
   ```
   Questo comando stampa le righe dalla 1 alla 5 del file `x.conf`. L'opzione `-n` impedisce a `sed` di stampare tutte le righe, mentre `p` indica di stampare solo le righe specificate.

2. **Stampare dalla riga 5 fino alla fine del file**
   - Puoi anche stampare dalla riga 5 fino alla fine del file usando il simbolo `$` per indicare la fine.
   ```bash
   sed -n '5,$p' x.conf
   ```
   Questo comando stampa dalla riga 5 fino alla fine del file.

3. **Sostituzione di testo**
   - `sed` è comunemente usato per sostituire testo all'interno di un file. Puoi utilizzare l'opzione `-i` per modificare il file in loco e creare un backup dell'originale.
   ```bash
   sed -i.bak 's/vecchio/nuovo/g' x.conf
   ```
   Questo comando sostituisce tutte le occorrenze della parola "vecchio" con "nuovo" nel file `x.conf`, creando un backup chiamato `x.conf.bak`.

4. **Eliminazione di righe commentate**
   - Per rimuovere le righe che iniziano con un cancelletto (commenti), puoi utilizzare il seguente comando:
   ```bash
   sed -i.bak '/^#/d' x.conf
   ```
   Qui, `^#` indica che la riga inizia con un cancelletto, e `d` indica di eliminare quelle righe. Questo comando crea anche un backup del file originale.

5. **Sostituzione con backup della data**
   - Se desideri creare un backup con la data corrente nel nome del file, puoi utilizzare il comando:
   ```bash
   sed -i.$(date +%Y%m%d) '/^#/d' x.conf
   ```
   Questo comando rimuove le righe commentate e crea un backup del file originale con la data nel formato `YYYYMMDD`.

#### Situazioni d'uso
- **Modifica di file di configurazione:** `sed` è spesso utilizzato per modificare file di configurazione in modo automatizzato, come l'aggiunta o la rimozione di opzioni.
- **Eliminazione di commenti:** È utile per ripulire file di configurazione da commenti non necessari prima di eseguire un'applicazione.
- **Sostituzioni di testo:** Può essere utilizzato per aggiornare valori in file di testo, come indirizzi IP o nomi di host.

## References

- 