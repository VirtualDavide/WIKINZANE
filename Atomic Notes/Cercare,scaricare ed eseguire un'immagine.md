docker 2025-03-23 21:18

Tags : [[Docker]] [[DailyLinux]]

# Cercare,scaricare ed eseguire un'immagine

###  Cercare un'immagine Docker

Puoi cercare un'immagine Docker utilizzando il comando `docker search` seguito dal nome dell'immagine o da una parola chiave. Ad esempio, per cercare immagini relative a "nginx", puoi usare:

```bash
docker search nginx
```

Questo comando restituirà un elenco di immagini disponibili su Docker Hub, insieme a una breve descrizione.

### Scaricare un'immagine Docker

Per scaricare un'immagine Docker, utilizza il comando `docker pull` seguito dal nome dell'immagine. Ad esempio, per scaricare l'immagine di nginx, puoi eseguire:

```bash
docker pull nginx
```

Se desideri scaricare una versione specifica di un'immagine, puoi specificare il tag dell'immagine. Ad esempio, per scaricare la versione 1.19 di nginx, utilizza:

```bash
docker pull nginx:1.19
```

Se non specifichi un tag, Docker scaricherà l'immagine con il tag `latest` per impostazione predefinita.

### Eseguire un'immagine Docker

Dopo aver scaricato l'immagine, puoi eseguirla utilizzando il comando `docker run`. Ad esempio, per eseguire l'immagine di nginx, puoi usare:

```bash
docker run -d -p 80:80 nginx
```

In questo comando:
- `-d` esegue il contenitore in modalità "detached" (in background).
- `-p 80:80` mappa la porta 80 del contenitore alla porta 80 della tua macchina host.
### Esempio completo

Ecco un esempio completo di come cercare, scaricare ed eseguire un'immagine Docker:

1. Cerca l'immagine nginx:
   ```bash
   docker search nginx
   ```

2. Scarica la versione 1.19 di nginx:
   ```bash
   docker pull nginx:1.19
   ```

3. Esegui l'immagine nginx:
   ```bash
   docker run -d -p 80:80 nginx:1.19
   ```

Ora dovresti avere un contenitore nginx in esecuzione sulla tua macchina, accessibile tramite il browser all'indirizzo `http://localhost`.

## References

- [[Installazione Docker]]
- [[Elencare,ispezionare e rimuovere le immagini]]
- [[Manifest file e supporto alle diverse architetture]]