2025-04-26 22:35

Tags : [[Comandi GNU e Unix]] / [[103.2]]

# Comando tr

Il comando `tr` (translate) lavora direttamente con i caratteri e può essere utilizzato per diverse operazioni, come convertire lettere minuscole in maiuscole, sostituire caratteri o rimuovere caratteri indesiderati.

#### Esempi di utilizzo di `tr`

1. **Convertire in maiuscolo**:
   - Se hai un file chiamato `text.txt` e vuoi convertirne il contenuto in maiuscolo, puoi usare:
     ```bash
     cat text.txt | tr 'a-z' 'A-Z'
     ```
   - Questo comando tradurrà tutti i caratteri minuscoli in maiuscoli.

2. **Sostituire caratteri**:
   - Puoi anche sostituire un carattere con un altro. Ad esempio, per sostituire la lettera "r" con "R":
     ```bash
     cat text.txt | tr 'r' 'R'
     ```
   - Se vuoi sostituire "r" con un'altra lettera, ad esempio "b", puoi fare:
     ```bash
     cat text.txt | tr 'r' 'b'
     ```

3. **Rimuovere caratteri**:
   - Se desideri rimuovere un carattere specifico, ad esempio i puntini di sospensione "...", puoi usare l'opzione `-d`:
     ```bash
     cat text.txt | tr -d '.'
     ```
   - Questo comando eliminerà tutti i punti dal file.

4. **Rimuovere più caratteri**:
   - Puoi rimuovere più caratteri specificando tutti i caratteri che vuoi eliminare. Ad esempio, per rimuovere sia i punti che i punti esclamativi:
     ```bash
     cat text.txt | tr -d '!.'
     ```

5. **Utilizzare il complementare**:
   - Puoi anche utilizzare l'opzione `-c` per mantenere solo i caratteri specificati. Ad esempio, per mantenere solo i punti:
     ```bash
     cat text.txt | tr -c '.' '\n'
     ```
   - Questo comando stamperà solo i punti, uno per riga.

6. **Eliminare caratteri non stampabili**:
   - Un uso comune di `tr` è quello di eliminare caratteri non stampabili. Puoi farlo con:
     ```bash
     cat text.txt | tr -cd '\11\12\15\40-\176'
     ```
   - Questo comando manterrà solo i caratteri stampabili.

7. **Sostituire caratteri di nuova riga con spazi**:
   - Se vuoi sostituire i caratteri di nuova riga con spazi, puoi usare:
     ```bash
     cat text.txt | tr '\n' ' '
     ```
   - Questo comando unirà tutte le righe in una sola, separandole con uno spazio.

8. **Sostituzione di sequenze di caratteri**:
   - Puoi anche sostituire sequenze di caratteri. Ad esempio, per sostituire "ciao" con "salve":
     ```bash
     cat text.txt | tr 'ciao' 'salve'
     ```
   - Ricorda che `tr` lavora su singoli caratteri, quindi non sostituisce sequenze di caratteri.

### Opzioni utili

Puoi sempre consultare l'help del comando `tr` per vedere tutte le opzioni disponibili:

```bash
tr --help
```

Questo ti darà un elenco delle opzioni e delle funzionalità che puoi utilizzare con `tr`.


## References

- [[Head e Tail]]