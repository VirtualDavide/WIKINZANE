2025-04-04 15:25

Tags : [[Docker]]

# Web App DB persistente -  Docker Volumi

### Struttura del Docker Compose

Il file `docker-compose.yml` definisce i servizi, i volumi e le configurazioni necessarie per eseguire l'applicazione. Ogni servizio ha un'immagine specificata, un nome del container, porte esposte e variabili d'ambiente. Nel caso del servizio Mealie, viene utilizzata l'immagine `ghcr.io/mealie-recipes/mealie:v1.11.0`, con la porta `9925` dell'host mappata alla porta `9000` del container. È anche impostato un limite di memoria di `500M` per il container.

### Esempio di Servizio Mealie

```YAML
services:
  mealie:
    image: ghcr.io/mealie-recipes/mealie:v1.11.0 # 
    container_name: mealie
    restart: always
    ports:
        - "9925:9000" # 
    deploy:
      resources:
        limits:
          memory: 500M # 
    volumes:
      - mealie-data:/app/data/
    environment:
      # Set Backend ENV Variables Here
      ALLOW_SIGNUP: false
      PUID: 1000
      PGID: 1000
      TZ: Europe/Rome
      MAX_WORKERS: 1
      WEB_CONCURRENCY: 1
      BASE_URL: https://localhost

  debug:
    image: ubuntu
    entrypoint: "bash -c 'while true; do sleep 1; done'"
    volumes:
      - mealie-data:/mnt/mealie

volumes:
  mealie-data:
```

Il servizio Mealie è un gestionale per le ricette e presenta una configurazione che include variabili d'ambiente per personalizzare il comportamento dell'applicazione. Tra queste, si trova la disabilitazione della registrazione degli utenti e l'impostazione del fuso orario. Il volume `mealie-data` è montato nella directory `/app/data/` del container, consentendo la persistenza dei dati.

### Servizio di Debug

Un secondo servizio, chiamato `debug`, utilizza un'immagine di Ubuntu e mantiene un ciclo infinito per rimanere attivo. Questo servizio monta lo stesso volume `mealie-data` nella directory `/mnt/mealie`, permettendo l'accesso ai dati persistenti dal container di debug. Questa configurazione dimostra come i volumi possano essere condivisi tra più container, facilitando l'accesso e la modifica dei dati.

### Procedura di Migrazione

Per iniziare, è necessario identificare il nome del container e il volume associato. Utilizzando il comando `docker volume inspect`, si può determinare la posizione fisica del volume. Una volta individuata la cartella, si può copiare su un altro host utilizzando `scp`, sfruttando un collegamento SSH attivo. Dopo aver verificato che i dati siano stati copiati correttamente sulla macchina Fedora, si procede a creare un volume con lo stesso nome in Podman utilizzando il comando `podman volume create`.

Successivamente, è importante controllare la posizione fisica del volume creato e trasferire il contenuto della cartella copiata nel nuovo volume. Una volta completato il trasferimento, si può avviare il container di Mealie su Fedora utilizzando la stessa configurazione del Docker Compose originale. Se tutto va a buon fine, l'applicazione dovrebbe avviarsi con gli stessi dati migrati.

### Gestione dei Dati Senza Volume

Un altro scenario discusso riguarda la creazione di un container che inizia a generare dati senza avere un volume associato. In questo caso, se il container viene eliminato, i dati andranno persi. Per evitare questa situazione, è fondamentale utilizzare volumi non appena si inizia a scrivere dati che si desidera mantenere.

Nel caso specifico del container di debug basato su Ubuntu, si può accedere alla home directory per verificare la presenza di file. Se si scopre che i dati non sono associati a un volume, è possibile utilizzare `docker inspect` per accedere ai dettagli del container e individuare i percorsi dei file nel filesystem overlay di Docker. Anche se i file sono accessibili, questa non è una pratica consigliata, poiché lavorare in questo modo è rischioso.

*esempio:*
![[mealie.zip]]
## References

- [[Elencare, ispezionare e rimuovere volumi]]