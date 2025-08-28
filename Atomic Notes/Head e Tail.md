2025-04-26 22:20

Tags : [[Comandi GNU e Unix]] / [[103.2]]

# Head e Tail

### Comando `head`

Il comando `head` è utilizzato per visualizzare le prime righe di un file. Ad esempio, se hai un file di log e vuoi vedere l'inizio, puoi utilizzare:

```bash
sudo head /var/log/messages
```

Questo comando stamperà le prime dieci righe del file `messages`. Puoi anche specificare quante righe visualizzare utilizzando l'opzione `-n`. Ad esempio, per vedere le prime cinque righe:

```bash
sudo head -n 5 /var/log/messages
```

### Comando `tail`

Il comando `tail`, al contrario di `head`, mostra le ultime righe di un file. Per esempio, per visualizzare le ultime dieci righe di un file di log, puoi usare:

```bash
sudo tail /var/log/messages
```

Puoi anche specificare il numero di righe da visualizzare con l'opzione `-n`, ad esempio:

```bash
sudo tail -n 5 /var/log/messages
```

#### Opzione `-f` (follow)

Una delle opzioni più utili di `tail` è `-f`, che permette di seguire un file in tempo reale. Questo è particolarmente utile per monitorare i log mentre vengono aggiornati. Ad esempio:

```bash
tail -f test1.txt
```

Se aggiungi nuove righe al file `test1.txt`, `tail -f` mostrerà automaticamente le nuove righe in tempo reale.
### Opzione `-F`

Se vuoi seguire un file che potrebbe non esistere al momento dell'esecuzione del comando, puoi usare l'opzione `-F` (maiuscola). Questo comando avviserà se il file non esiste, ma inizierà a seguirlo non appena verrà creato:

```bash
tail -F test2.txt
```

Se `test2.txt` non esiste, `tail` mostrerà un messaggio di errore, ma continuerà a monitorare e seguirà il file non appena verrà creato.

### Monitoraggio di più file

Puoi anche monitorare più file contemporaneamente con `tail`:

```bash
tail -f test1.txt test2.txt
```

Questo comando mostrerà le ultime righe di entrambi i file e continuerà a monitorarli.

### Opzione `-q` (quiet)

Se non ti interessa sapere da quale file provengono le righe, puoi utilizzare l'opzione `-q` (quiet) per nascondere l'intestazione:

```bash
tail -f -q test1.txt test2.txt
```

In questo modo, quando aggiungi righe a entrambi i file, non verrà mostrato il nome del file, rendendo l'output più compatto.

## References

- [[Le meraviglie di Cut]]
- [[Comando tr]]