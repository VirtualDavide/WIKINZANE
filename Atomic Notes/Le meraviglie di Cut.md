2025-04-26 22:07

Tags : [[Comandi GNU e Unix]] / [[103.2]]

# Le meraviglie di Cut

Il comando `cut` è utilizzato per estrarre sezioni di testo da file o output di comandi. È importante non confonderlo con il comando `cat`, che serve a concatenare o visualizzare il contenuto di un file.

#### Esempi di utilizzo di `cut`

1. **Estrazione di colonne**:
   - Per estrarre una colonna specifica da un file, puoi usare:
     ```bash
     cut -f2 cut_example.txt
     ```
     Questo comando stamperà la seconda colonna di ogni riga del file `cut_example.txt`.

2. **Estrazione di un range di colonne**:
   - Puoi anche specificare un range di colonne:
     ```bash
     cut -c12-15 cut_example.txt
     ```
     Questo comando estrarrà i caratteri dalla colonna 12 alla colonna 15.

3. **Estrazione da un delimitatore**:
   - Se i dati sono separati da un delimitatore (ad esempio, i due punti `:` nel file `/etc/passwd`), puoi specificare il delimitatore e il campo da estrarre:
     ```bash
     cut -d: -f1 /etc/passwd
     ```
     Questo comando stamperà il primo campo (l'utente) di ogni riga del file `/etc/passwd`.

4. **Utilizzo di `cut` con `cat` e pipe**:
   - Puoi combinare `cat` e `cut` utilizzando il carattere pipe (`|`) per filtrare l'output di un comando:
     ```bash
     cat /etc/passwd | cut -d: -f1
     ```
     Questo comando mostrerà solo gli utenti dal file `/etc/passwd`.

5. **Ordinamento dell'output**:
   - Puoi anche ordinare l'output utilizzando il comando `sort`:
     ```bash
     cat /etc/passwd | cut -d: -f1 | sort
     ```
     Questo comando stamperà gli utenti in ordine alfabetico.

6. **Estrazione di più campi**:
   - Puoi estrarre più campi specificando i numeri dei campi:
     ```bash
     cut -d: -f1,7 /etc/passwd
     ```
     Questo comando stamperà il primo e il settimo campo (utente e shell) di ogni riga.

7. **Filtraggio con condizioni**:
   - Puoi anche filtrare l'output in base a condizioni specifiche. Ad esempio, per stampare solo le righe che contengono una maiuscola:
     ```bash
     cat /etc/passwd | grep [A-Z] | cut -d: -f1
     ```

8. **Sostituzione del delimitatore**:
   - Puoi sostituire il delimitatore dell'output con un altro carattere:
     ```bash
     cut -d: -f1,7 /etc/passwd --output-delimiter="#"
     ```
     Questo comando stamperà il primo e il settimo campo separati da un cancelletto (`#`).

9. **Utilizzo dell'opzione `--complement`**:
   - L'opzione `--complement` consente di stampare tutto tranne i campi o le colonne specificate. Ad esempio, per escludere la seconda colonna:
     ```bash
     cut -d: --complement -f2 cut_example.txt
     ```
     Questo comando stamperà tutto tranne la seconda colonna.
   - Se vuoi escludere un range di colonne, ad esempio dalla colonna 1 alla colonna 2:
     ```bash
     cut -d: --complement -f1-2 cut_example.txt
     ```
     Questo comando stamperà solo le colonne rimanenti.

## References

- [[Dividere ed unire i file con split e cat]]
- [[Head e Tail]]