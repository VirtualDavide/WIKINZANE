2025-03-23 21:28

Tags : [[Docker]]

# Elencare,ispezionare e rimuovere le immagini

Per elencare,ispezionare e rimuovere le immagini Docker utilizziamo i seguenti comandi : `image ls`, `history`, `inspect` e `rmi`.

### 1. `docker image ls`

**Descrizione**: Questo comando elenca tutte le immagini Docker presenti nel tuo sistema.

**Sintassi**:
```bash
docker image ls [OPTIONS]
```

**Opzioni comuni**:
- `-a` o `--all`: Mostra tutte le immagini, comprese quelle non taggate.
- `--filter`: Filtra l'elenco delle immagini in base a criteri specifici.
- `--format`: Consente di formattare l'output in base a un modello specificato.

**Esempio**:
```bash
docker image ls
```

### 2. `docker history`

**Descrizione**: Mostra la cronologia dei comandi utilizzati per creare un'immagine Docker specifica. Questo comando è utile per comprendere come è stata costruita un'immagine e quali modifiche sono state apportate.

**Sintassi**:
```bash
docker history [OPTIONS] IMAGE
```

**Opzioni comuni**:
- `--no-trunc`: Mostra informazioni complete senza troncamento.

**Esempio**:
```bash
docker history nginx
```

### 3. `docker inspect`

**Descrizione**: Fornisce dettagli completi su un'immagine, un contenitore o un altro oggetto Docker. L'output è in formato JSON e include informazioni come configurazioni, stato, porte esposte e altro.

**Sintassi**:
```bash
docker inspect [OPTIONS] NAME|ID [NAME|ID...]
```

**Opzioni comuni**:
- `--format`: Consente di specificare un modello per filtrare l'output.

**Esempio**:
```bash
docker inspect nginx
```

### 4. `docker rmi`

**Descrizione**: Rimuove una o più immagini Docker dal sistema. Questo comando è utile per liberare spazio o rimuovere immagini non più necessarie.

**Sintassi**:
```bash
docker rmi [OPTIONS] IMAGE [IMAGE...]
```

**Opzioni comuni**:
- `-f` o `--force`: Forza la rimozione dell'immagine, anche se è utilizzata da un contenitore.
- `--no-prune`: Non rimuove le immagini genitore se l'immagine è un'immagine figlia.

**Esempio**:
```bash
docker rmi nginx
```


Questi comandi sono fondamentali per la gestione delle immagini Docker. `docker image ls` ti consente di visualizzare le immagini disponibili, `docker history` ti mostra come è stata costruita un'immagine, `docker inspect` fornisce dettagli approfonditi e `docker rmi` ti permette di rimuovere immagini non più necessarie. Se hai ulteriori domande o hai bisogno di chiarimenti, non esitare a chiedere!
## References

- [[Cercare,scaricare ed eseguire un'immagine]]