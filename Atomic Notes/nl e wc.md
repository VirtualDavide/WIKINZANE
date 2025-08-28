2025-04-26 22:38

Tags : [[Comandi GNU e Unix]] / [[103.2]]

# nl e wc

Ciao! Ecco una spiegazione basata sul video che hai descritto, con i comandi da terminale utilizzati.

---

### Introduzione ai Filtri di Testo in Linux

In questo video, abbiamo esplorato alcuni comandi utili per il conteggio e la manipolazione di flussi di testo in Linux, focalizzandoci principalmente su `nl` e `wc`.

### Comando `nl`

Il comando `nl` (number lines) è utilizzato per numerare le righe di un file di testo. Può essere utilizzato in vari modi:

1. **Numerazione di base**:
   ```bash
   nl nomefile.txt
   ```
   Questo comando aggiunge un contatore accanto a ogni riga del file `nomefile.txt`.

2. **Incremento personalizzato**:
   Se desideri incrementare il contatore di un valore diverso da uno, puoi utilizzare l'opzione `-i`:
   ```bash
   nl -i 2 nomefile.txt
   ```
   Questo incrementerà il contatore di 2 (1, 3, 5, 7, ...).

3. **Separatore personalizzato**:
   Puoi anche specificare un separatore diverso dalla tabulazione tra il numero di riga e il contenuto della riga utilizzando l'opzione `-s`:
   ```bash
   nl -s "." nomefile.txt
   ```
   Questo utilizzerà un punto come separatore.

4. **Posizione del numero di riga**:
   Con l'opzione `-v`, puoi specificare in quale colonna visualizzare il numero di riga:
   ```bash
   nl -w 2 nomefile.txt
   ```
   Questo sposterà il numero di riga nella seconda colonna.

5. **Numerazione con zeri**:
   Se desideri una numerazione con zeri iniziali, puoi utilizzare l'opzione `-z`:
   ```bash
   nl -z nomefile.txt
   ```
   Questo formatterà i numeri con zeri iniziali (0001, 0002, ...).

### Comando `wc`

Il comando `wc` (word count) è utilizzato per contare righe, parole e byte in un file di testo. Può essere utilizzato come segue:

1. **Conteggio di righe, parole e byte**:
   ```bash
   wc nomefile.txt
   ```
   Questo comando restituisce il numero di righe, parole e byte nel file `nomefile.txt`.

2. **Conteggio delle parole**:
   Se desideri contare solo le parole, puoi utilizzare l'opzione `-w`:
   ```bash
   wc -w nomefile.txt
   ```

3. **Conteggio della lunghezza della riga più lunga**:
   Per ottenere la lunghezza della riga più lunga, puoi utilizzare l'opzione `-L`:
   ```bash
   wc -L nomefile.txt
   ```

4. **Conteggio dei byte**:
   Per contare solo i byte, puoi utilizzare l'opzione `-c`:
   ```bash
   wc -c nomefile.txt
   ```

## References

- [[Head e Tail]]
- [[Comando tr]]