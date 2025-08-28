2025-04-04 15:44

Tags : [[Docker]]

# Esporre (non esporre un servizio)

### Configurazione Iniziale

Dopo aver lanciato lo stack con il comando `docker-compose up`, possiamo verificare che Nginx sia in esecuzione e in ascolto su tutte le interfacce di rete (0.0.0.0) sulla porta 80. Questo significa che chiunque sulla stessa rete, o chiunque abbia accesso al tuo indirizzo IP, può raggiungere il servizio. Se desideriamo limitare l'accesso in modo che solo il sistema host possa accedere al servizio, dobbiamo modificare la configurazione.

### Limitare l'Accesso al Servizio

Per limitare l'accesso al servizio, dobbiamo specificare l'indirizzo IP di localhost (127.0.0.1) nel file `docker-compose.yml`. La sintassi per farlo è la seguente:

```
127.0.0.1:80:80
127.0.0.1:443:443
```

Dopo aver apportato questa modifica, è necessario fermare lo stack con `docker-compose down` e riavviarlo con `docker-compose up`. Ora, il servizio sarà accessibile solo dal sistema host, mentre gli altri utenti sulla rete non potranno raggiungerlo. Possiamo confermare questa modifica eseguendo `docker ps`, dove vedremo che le porte esposte non sono più 0.0.0.0, ma 127.0.0.1.

### Allocazione Dinamica delle Porte

Un'altra considerazione importante è la gestione di più stack che potrebbero richiedere l'uso delle stesse porte. Se abbiamo più servizi in esecuzione, è possibile che le porte riservate sull'host non siano disponibili. Per evitare conflitti, possiamo esporre le porte senza specificare su quale porta dell'host devono essere mappate.

Modificando il file `docker-compose.yml` per esporre solo le porte 80 e 443 senza specificare le porte dell'host, Docker assegnerà automaticamente porte casuali disponibili. Ad esempio, potremmo vedere porte come 32771 mappate sulla porta 80 e 32772 sulla porta 443. Queste porte sono completamente casuali e sequenziali, il che significa che non dobbiamo preoccuparci di conflitti con altre istanze in esecuzione.

*esempio*
![[php-nginx-docker.zip]]
## References

- [[Modalità di Networking - Drivers]]
- [[Reti Virtuali - Docker]]