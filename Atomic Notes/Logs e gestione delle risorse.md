2025-03-24 18:13

Tags : [[Docker]]

# Logs e gestione delle risorse

### Comandi Docker

#### 1. `docker logs`
Il comando `docker logs` viene utilizzato per visualizzare i log di un container Docker. Questo comando è utile per il debug e per monitorare l'output delle applicazioni in esecuzione all'interno del container. La sintassi di base è:

```
docker logs [OPTIONS] CONTAINER
```

Dove `CONTAINER` è l'ID o il nome del container di cui si vogliono visualizzare i log. Alcune opzioni comuni includono:

- `--tail`: Mostra solo le ultime N righe dei log.
- `--since`: Mostra i log a partire da un certo momento.
- `--timestamps`: Mostra i timestamp nei log.

#### 2. `docker logs -f`
L'opzione `-f` (o `--follow`) permette di seguire in tempo reale i log di un container. Utilizzando questo comando, puoi vedere i log man mano che vengono generati, il che è particolarmente utile per il monitoraggio delle applicazioni in esecuzione. La sintassi è:

```
docker logs -f CONTAINER
```

#### 3. `docker kill`
Il comando `docker kill` viene utilizzato per terminare un container in esecuzione in modo immediato. A differenza di `docker stop`, che invia un segnale di arresto e attende che il container si fermi in modo ordinato, `docker kill` invia un segnale di terminazione (di default, `SIGKILL`) al processo principale del container. La sintassi è:

```
docker kill [OPTIONS] CONTAINER
```

Dove `CONTAINER` è l'ID o il nome del container da terminare. Puoi anche specificare un segnale diverso da inviare utilizzando l'opzione `-s`:

```
docker kill -s SIGTERM CONTAINER
```

#### 4. `--cpus`
L'opzione `--cpus` consente di limitare l'uso della CPU da parte di un container. Puoi specificare il numero di CPU che il container può utilizzare. Ad esempio, se vuoi limitare un container a utilizzare solo 0.5 CPU, puoi utilizzare:

```
docker run --cpus=".5" IMAGE
```

Questa opzione è utile per gestire le risorse del sistema e garantire che un singolo container non monopolizzi la CPU.

#### 5. `--memory`
L'opzione `--memory` consente di limitare la quantità di memoria RAM che un container può utilizzare. Puoi specificare la quantità di memoria in vari formati, come megabyte (M) o gigabyte (G). Ad esempio, per limitare un container a 512 megabyte di RAM, puoi utilizzare:

```
docker run --memory="512m" IMAGE
```

Questa opzione è fondamentale per evitare che un container consumi tutta la memoria disponibile, il che potrebbe influire sulle prestazioni del sistema e di altri container.

### Conclusione
Questi comandi e opzioni sono strumenti essenziali per la gestione e il monitoraggio dei container Docker, permettendo di controllare l'output delle applicazioni, gestire le risorse e terminare i container in modo efficace.
## References

- [[Elencare e gestire le immagini]]