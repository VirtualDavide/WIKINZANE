2025-04-04 16:06

Tags : [[Docker]]

# Reti Virtuali - Docker

Nel contesto di Docker, la creazione e la gestione di reti virtuali è fondamentale per garantire una comunicazione sicura e isolata tra i container. Di seguito, esploreremo come configurare reti virtuali utilizzando i due esempi forniti e come visualizzare e rimuovere le reti create.

### Esempio di Configurazione delle Reti

Nel primo esempio, abbiamo due servizi: `php` e `nginx`. Nginx espone le porte 8080 e 8443, e entrambi i servizi condividono un volume per la directory dell'applicazione. Inoltre, Nginx è configurato per utilizzare due reti: la rete predefinita e una rete personalizzata chiamata `rete_nginx`.

```yaml
services:
  php:
    image: 'php:8.1-fpm'
    container_name: php-testNetwork
    volumes:
      - './app:/var/www/html'

  nginx:
    image: 'nginx:latest'
    container_name: nginx-testNetwork
    ports:
      - '8080:80'
      - '8443:443'
    volumes:
      - './app:/var/www/html:ro'
      - './config/nginx:/etc/nginx/conf.d'
    depends_on:
      - php
    networks:
      - default
      - nginx

networks:
  nginx:
    name: rete_nginx
```

In questo esempio, la rete `rete_nginx` consente ai container di comunicare tra loro in modo isolato, mentre il servizio PHP è accessibile tramite Nginx.

Nel secondo esempio, abbiamo un servizio di debug basato su Ubuntu che utilizza una rete esterna chiamata `nginx-network`, oltre alla rete predefinita. Questo consente al container di debug di comunicare con i servizi sulla rete `rete_nginx`.

```yaml
services:
  debug:
    image: ubuntu
    entrypoint: "bash -c 'while true; do sleep 1; done'"
    networks:
      - nginx-network
      - default

networks:
  nginx-network:
    name: rete_nginx
    external: true
```

la direttiva `external: true` dice a compose di cercare una rete con il nome indicato definita esternamente, invece di cercare di crearne una con quel nome all'avvio dello stack.  
Questo è necessario se si vuole mettere in comunicazione più stack di Compose su una rete comune definita manualmente con "docker network create" o in un "docker-compose.yml" separato dove la rete è stata definita senza la direttiva "external: true".

All'interno delle reti inseriamo anche la rete di default, poiché il docker compose, nella sezione *networks*, non va ad aggiungere le nuove reti che indichiamo, bensì a sovrascriverle 
``
### Visualizzazione delle Reti Virtuali

Per visualizzare le reti virtuali create in Docker, puoi utilizzare il comando:

```bash
docker network ls
```

Questo comando mostrerà un elenco di tutte le reti disponibili, incluse quelle predefinite e quelle personalizzate. Le informazioni mostrate includeranno il nome della rete, il suo ID e il driver utilizzato.

### Rimozione delle Reti Virtuali

Se desideri rimuovere una rete virtuale, puoi utilizzare il comando:

```bash
docker network rm nome_rete
```

Sostituisci `nome_rete` con il nome della rete che desideri eliminare. È importante notare che non puoi rimuovere una rete se ci sono container ad essa collegati. Pertanto, assicurati di fermare e rimuovere i container associati prima di tentare di eliminare la rete.

*esempio:*
![[external-network-ubuntu.zip]]
![[external-network-nginx-plus-php.zip]]
## References

- [[Modalità di Networking - Drivers]]