2025-04-03 22:08

Tags : [[Docker]] [[DailyLinux]]

# Docker compose

### Introduzione a Docker Compose

Docker Compose è uno strumento che semplifica la gestione di applicazioni composte da più container Docker. **Consente di definire e gestire un intero stack di servizi in un unico file di configurazione, evitando la necessità di eseguire comandi complessi e ripetitivi da riga di comando**. Con Docker Compose, puoi avviare, fermare e gestire più container come un'unica unità.

### Creazione di un File `docker-compose.yml`

Per iniziare a utilizzare Docker Compose, devi creare un file di testo chiamato `docker-compose.yml` (o `docker-compose.yaml`). Questo file utilizza il formato *YAML*, che è sensibile all'indentazione. Ecco i campi principali da includere nel file:

1. **version**: Specifica la versione del formato di Docker Compose da utilizzare.
2. **services**: Definisce i servizi (*container*) che compongono l'applicazione.
3. **container_name**: (opzionale) Specifica un nome personalizzato per il container.
4. **image**: Indica l'immagine Docker da utilizzare per il servizio.
5. **ports**: Mappa le porte del container a quelle dell'host.
6. **volumes**: Monta directory o file dall'host nel container.
7. **depends_on**: Specifica le dipendenze tra i servizi.

**Esempio di File `docker-compose.yml`:**
```yaml
version: '3.8'

services:
  nginx:
    container_name: my-nginx
    image: nginx:latest
    ports:
      - "8080:80"
    volumes:
      - ./app:/usr/share/nginx/html
      - ./config/nginx.conf:/etc/nginx/nginx.conf

  php:
    container_name: my-php
    image: php:8.1-fpm
    volumes:
      - ./app:/var/www/html

  mariadb:
    container_name: my-mariadb
    image: mariadb:latest
    environment:
      MYSQL_ROOT_PASSWORD: my-secret-pw
    volumes:
      - db_data:/var/lib/mysql

```

- **version**: Indica la versione del file di configurazione. È importante per garantire la compatibilità con le funzionalità di Docker Compose.
- **services**: Qui definisci i vari servizi che compongono la tua applicazione. Ogni servizio rappresenta un container.
- **container_name**: Consente di assegnare un nome specifico al container, facilitando la gestione.
- **image**: Specifica l'immagine Docker da utilizzare per il servizio. Puoi anche specificare una versione.
- **ports**: Mappa le porte del container a quelle dell'host, consentendo l'accesso ai servizi esposti.
- **volumes**: Monta directory o file dall'host nel container, permettendo la persistenza dei dati e la condivisione di file.
- **depends_on**: Definisce l'ordine di avvio dei servizi, assicurando che un servizio venga avviato solo dopo che le sue dipendenze sono pronte.

### Esecuzione e Fermata di un Stack con Docker Compose

Per avviare l'intero stack definito nel file `docker-compose.yml`, utilizza il seguente comando:

```bash
docker-compose up
```

Se desideri eseguire i container in background (modalità detached), puoi aggiungere l'opzione `-d`:

```bash
docker-compose up -d
```

Per fermare e rimuovere i container, le reti e i volumi creati da `docker-compose up`, utilizza il comando:

```bash
docker-compose down
```

Questo comando è molto utile perché ti consente di fermare e rimuovere tutti i servizi definiti nel file `docker-compose.yml` con un solo comando, senza dover fermare ogni container singolarmente.

### Conclusione

Docker Compose è uno strumento potente per gestire applicazioni multi-container. Creando un file `docker-compose.yml`, puoi definire facilmente i servizi, le loro configurazioni e le dipendenze. Con pochi comandi, puoi avviare e fermare l'intero stack, semplificando notevolmente il processo di sviluppo e gestione delle applicazioni Docker.

*esempio* : ![[stack-LEMP-TODO_App.zip]]
## References

- [[Variabili d'ambiente e restart policy]]