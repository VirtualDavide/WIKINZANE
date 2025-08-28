2025-07-24 15:06

Tags : [[Linux LPI - 101]] [[103.3]]

# Archiviazione e compressione di file e cartelle

In Linux, **archiviazione** e **compressione** sono due processi distinti, contrariamente a quanto si può pensare in Windows dove la compressione e l'archiviazione sono spesso combinati (come nel caso dei file ZIP).

- **Archiviazione**: Il processo di aggregazione di più file e directory in un unico file. Questo è fatto principalmente per organizzare i dati e facilitare il loro trasferimento o salvataggio.
- **Compressione**: Il processo di riduzione della dimensione di un file o di un archivio, rendendoli più piccoli e facili da gestire.
### Comandi Utilizzati

1. **gzip**: Comprime un file, sostituendolo con una versione compressa (`.gz`).

```bash
gzip syslog
```
    
2. **xz**: Offre un rapporto di compressione migliore rispetto a gzip, ma richiede più risorse.
    
    `xz syslog`
    
3. **tar**: Crea un archivio da più file/directory, spesso combinato con gzip o xz.
    
    `tar -czvf var.tar.gz var tar -cJvf var.tar.xz var`
    
4. **cat**: Visualizza il contenuto di un file non compresso.
    
    `cat syslog`
    
5. **zcat**: Visualizza il contenuto di un file compresso con gzip.
    
    `zcat syslog.gz`
    
6. **ls**: Elenca file e directory con dettagli.
    
    `ls -l`
    
7. **du**: Mostra l'uso dello spazio su disco.
    
    `du -sh var`
    

### Esempi di Utilizzo

- **Comprimere un file**:
    
    `gzip syslog`
    
    Risultato: `syslog.gz`
    
- **Decomprimere un file**:
    
    `gunzip syslog.gz`
    
    Risultato: `syslog`
    
- **Visualizzare un file compresso**:
    
    `zcat syslog.gz`
    
- **Creare un archivio compresso**:
    
    `tar -czvf var.tar.gz var tar -cJvf var.tar.xz var`
    

### Estrazione di File Compressi

1. **Estrazione di un file compresso con gzip**:
    
    `gunzip syslog.gz`
    
2. **Estrazione di un file compresso con xz**:
    
    `unxz syslog.xz`
    
3. **Estrazione di un archivio tar compresso con gzip**:
    
    `tar -xzf var.tar.gz`
    
4. **Estrazione di un archivio tar compresso con xz**:
    
    `tar -xJf var.tar.xz`
    
5. **Estrazione in una directory specifica**:
    
    `tar -xzf var.tar.gz -C /path/to/destination`
    

### Parametri Utilizzati in tar

- `-x`: Estrae i file dall'archivio.
- `-z`: Usa gzip per decomprimere.
- `-J`: Usa xz per decomprimere.
- `-f`: Specifica il nome del file archivio.
- `-v`: Mostra i file mentre vengono estratti (verboso).
- `-C`: Specifica la directory di destinazione.

### Considerazioni Finali

- **Rapporto di compressione**: xz offre un rapporto migliore rispetto a gzip, ma richiede più risorse.
- **Archiviazione**: tar è utile per aggregare file/directory in un unico file, che può essere compresso.
- **Estrazione**: tar mantiene la struttura originale dei file e directory.
## References

- [[zcat,bzcat,xzcat]]