2025-08-21 17:01

Tags : [[DailyLinux]] [[Linux LPI - 101]] [[103.4]]

# bunzip2 - unxz

## Utility di Compressione e Decompressione in Linux

### Comandi per Estrarre File BZ2 e XZ

 **bzip2** e **xz**. Questi strumenti sono utili per gestire file compressi con estensioni .bz2 e .xz. Di seguito sono riportati i comandi utilizzati per estrarre i file e una spiegazione di ciascuno.

### Estrarre File BZ2
Per estrarre un file con estensione **.bz2**, si utilizza il comando **bzip2** con l'opzione **-d** (o **--decompress**). Tuttavia, poiché i file BZ2 sono spesso archiviati in un file tar, è comune utilizzare anche il comando **tar**.

**Esempio di utilizzo per estrarre un file BZ2:**
```bash
bzip2 -d prova.tar.bz2
```
Dopo aver estratto il file, se il file è un archivio tar, si utilizza il comando **tar** per estrarre il contenuto:
```bash
tar -xvf prova.tar
```
In questo caso, il file **prova.txt** viene estratto dall'archivio.

### Estrarre File XZ
Per estrarre un file con estensione **.xz**, si utilizza il comando **xz** con l'opzione **-d** (o **--decompress**). Anche in questo caso, se il file è un archivio tar, si utilizza il comando **tar**.

**Esempio di utilizzo per estrarre un file XZ:**
```bash
xz -d prova.tar.xz
```
Se il file è un archivio tar, si utilizza:
```bash
tar -xvf prova.tar
```
Dopo l'estrazione, il contenuto del file **prova.txt** sarà disponibile.

### Pulizia dei File Estratti
Dopo aver estratto i file, è buona pratica rimuovere i file compressi e gli archivi per mantenere il sistema pulito. I comandi per rimuovere i file sono:
```bash
rm prova.bz2
rm prova.tar
```
o
```bash
rm prova.xz
rm prova.tar
```

## References

- 