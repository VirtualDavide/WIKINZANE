2025-07-19 16:38

Tags : [[Linux LPI - 101]] [[103.2]]

# md5sum,sha265sum,sha512sum

### Concetti Chiave

1. **Verifica dell'Integrità dei File**:
   - È importante assicurarsi che un file scaricato non sia stato compromesso o alterato. Questo è particolarmente rilevante per file scaricati da internet.

2. **Hashing**:
   - L'hashing è un processo che genera una rappresentazione alfanumerica (hash) di un file. Questa rappresentazione è unica per il contenuto del file; anche una minima modifica nel file produce un hash completamente diverso.

3. **Algoritmi di Hashing**:
   - **MD5**: Un algoritmo di hashing comune, ma considerato meno sicuro rispetto ad altri algoritmi più recenti.
   - **SHA-256 e SHA-512**: Algoritmi di hashing più sicuri, utilizzati per garantire una maggiore integrità e sicurezza.

### Comandi Utilizzati

1. **Calcolo dell'Hash MD5**:
   - Per calcolare l'hash MD5 di un file, si utilizza il comando:
     ```bash
     md5sum nomefile.txt
     ```
   - Questo comando restituisce un hash MD5 che rappresenta il contenuto del file `nomefile.txt`.

2. **Calcolo dell'Hash SHA-256**:
   - Per calcolare l'hash SHA-256, si utilizza il comando:
     ```bash
     sha256sum nomefile.txt
     ```

3. **Calcolo dell'Hash SHA-512**:
   - Per calcolare l'hash SHA-512, si utilizza il comando:
     ```bash
     sha512sum nomefile.txt
     ```

### Esempio Pratico

- Se si calcola l'hash di un file chiamato `prova.txt` e si ottiene un certo valore, qualsiasi modifica al file (anche solo l'aggiunta di un punto) cambierà l'hash in modo significativo. Questo dimostra che il file è stato alterato.

### Conclusione

Il calcolo degli hash è un metodo efficace per garantire che i file siano stati trasferiti correttamente e non siano stati manomessi. Utilizzare algoritmi di hashing più sicuri come SHA-256 o SHA-512 è consigliato per una maggiore protezione.
## References

- 