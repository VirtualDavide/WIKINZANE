2025-03-23 21:34

Tags : [[Docker]]

# Manifest file e supporto alle diverse architetture

Non dovremmo mai installare a "caso" un'immagine docker sulle nostre macchine, ma dovremmo capire prima se tale immagine è supportata e con quali parametri può essere installata correttamente.

1. **Consultare Docker Hub**:
   - Prima di scaricare e utilizzare un'immagine Docker, è consigliabile visitare Docker Hub per ottenere informazioni dettagliate sull'immagine.
   - Le pagine delle immagini spesso contengono una sezione "How to Use this image" che fornisce istruzioni su come eseguire l'immagine con parametri specifici.

2. **Architetture Supportate**:
   - È importante controllare le architetture supportate dall'immagine, specialmente se si utilizza hardware non standard (ad esempio, Raspberry Pi).
   - Le architetture comuni includono:
     - `amd64`: architettura standard per la maggior parte dei computer.
     - `arm64`: per Raspberry Pi recenti (ARM v8).
     - `arm32`: per Raspberry Pi meno recenti (ARM v7).
     - Altre architetture come PowerPC e MIPS.

3. **Verifica delle Architetture da Riga di Comando**:
   - Puoi utilizzare il comando `docker manifest inspect` per interrogare il manifest di un'immagine e ottenere informazioni sulle architetture supportate.
   - Questo comando restituisce un output in formato JSON, che può essere filtrato con script in vari linguaggi di programmazione.

4. **Dettagli Aggiuntivi con il Flag Verbose**:
   - Aggiungendo il flag `--verbose` al comando `docker manifest inspect`, puoi ottenere informazioni più dettagliate sull'immagine, inclusi i layer e le dimensioni.

5. **Controllo delle Versioni**:
   - È utile controllare la versione di ciascuna immagine per assicurarsi che soddisfi i requisiti di un'applicazione specifica.

### Comandi Utilizzati

1. **Comando per Verificare il Manifest di un'Immagine**:
   ```bash
   docker manifest inspect nginx
   ```

2. **Comando per Ottenere Maggiori Dettagli**:
   ```bash
   docker manifest inspect --verbose nginx
   ```

### Esempio di Output

L'output del comando `docker manifest inspect` fornisce informazioni come:
- Architetture supportate (es. `amd64`, `arm64`, `arm32`, `s390x`, `ppc64le`, `mips`).
- Dimensioni dei layer dell'immagine.
- Informazioni sul manifest dell'immagine, inclusa la base su cui è costruita (ad esempio, Debian Bookworm slim).

![[docker-cheatsheet-1.pdf]]
## References

- [[Elencare,ispezionare e rimuovere le immagini]]
- [[Cercare,scaricare ed eseguire un'immagine]]