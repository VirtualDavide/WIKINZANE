2025-04-03 22:40

Tags : [[Docker]] [[DailyLinux]]

# Variabili d'ambiente e restart policy

### Utilizzo dei File `.env`

I file `.env` sono strumenti utili **per gestire le variabili d'ambiente in modo sicuro e organizzato**. Questi file consentono di separare le configurazioni sensibili, come le password, dalla configurazione del progetto, rendendo più facile la condivisione del codice senza esporre informazioni riservate.

**Esempio di File `.env`:**
```
# File .env
APT_NAME=todo
MYSQL_ROOT_PASSWORD=supersecretpassword
```

In questo esempio, abbiamo definito due variabili: `APT_NAME` e `MYSQL_ROOT_PASSWORD`. Queste variabili possono essere referenziate nel file `docker-compose.yml` utilizzando la sintassi `${VARIABILE}`.

**Esempio di Docker Compose:**
```yaml
version: '3.8'

services:
  php:
    image: mai-php
    container_name: ${APT_NAME}-php
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}

  nginx:
    image: nginx
    container_name: ${APT_NAME}-nginx

  mariadb:
    image: mariadb
    container_name: ${APT_NAME}-mariadb
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
```

In questo esempio, i nomi dei container e le variabili d'ambiente sono configurati utilizzando le variabili definite nel file `.env`. Questo approccio consente di mantenere il file `docker-compose.yml` pulito e facilmente configurabile.
### Politica di Restart

La politica di restart in Docker definisce come e quando un container deve essere riavviato in caso di arresto o errore. È possibile specificare diverse politiche di riavvio nel file `docker-compose.yml`.

**Opzioni di Politica di Restart:**
- `no`: (predefinito) non riavvia il container.
- `always`: riavvia il container indipendentemente dal motivo per cui è stato arrestato.
- `on-failure`: riavvia il container solo se termina con un errore. È possibile specificare un numero massimo di tentativi.
- `unless-stopped`: riavvia il container a meno che non sia stato arrestato manualmente.

**Esempio di Politica di Restart in Docker Compose:**
```yaml
version: '3.8'

services:
  php:
    image: mai-php
    container_name: ${APT_NAME}-php
    restart: always

  nginx:
    image: nginx
    container_name: ${APT_NAME}-nginx
    restart: unless-stopped

  mariadb:
    image: mariadb
    container_name: ${APT_NAME}-mariadb
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
    restart: on-failure:5
```

In questo esempio:
- Il servizio `php` verrà sempre riavviato, indipendentemente dal motivo per cui è stato arrestato.
- Il servizio `nginx` verrà riavviato a meno che non sia stato arrestato manualmente.
- Il servizio `mariadb` verrà riavviato solo se termina con un errore, fino a un massimo di 5 tentativi.

### Conclusione

L'uso dei file `.env` e delle politiche di restart in Docker Compose migliora la gestione delle configurazioni e la resilienza dei servizi. Utilizzando questi strumenti, è possibile creare ambienti di sviluppo e produzione più sicuri e robusti.
## References

- [[Docker compose]]