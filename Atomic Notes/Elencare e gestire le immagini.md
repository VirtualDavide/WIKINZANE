2025-03-24 18:02

Tags : [[Docker]]

# Elencare e gestire le immagini

1. **Container non Persi**: Quando un container viene terminato, non viene eliminato ma rimane in uno stato "fermo". Può essere riavviato in qualsiasi momento.

2. **Riavvio di un Container**: È possibile riavviare un container esistente utilizzando il comando `docker start <nome_container>`.

3. **Attaccarsi a un Container**: Si può tornare all'interno di un container in esecuzione con `docker attach <nome_container>`.

4. **Eliminazione di un Container**: Per eliminare un container, si utilizza il comando `docker rm <nome_container>` o `docker rm <ID_container>`.

5. **Esecuzione Temporanea**: Si può eseguire un container con l'opzione `--rm` per farlo eliminare automaticamente al termine dell'esecuzione.

6. **Visualizzazione dei Container**: Utilizzando `docker ps`, si possono vedere i container in esecuzione, mentre `docker ps -a` mostra anche quelli non più in esecuzione.

7. **Fermare un Container**: Per fermare un container in esecuzione, si utilizza `docker stop <nome_container>` o `docker stop <ID_container>`.

8. **Esecuzione in Background**: Per eseguire un container in modalità detached (in background), si utilizza `docker run -d <immagine>`.

### Comandi Docker Digitati:
- `docker start <nome_container>`: Riavvia un container esistente.
- `docker attach <nome_container>`: Si attacca a un container in esecuzione.
- `docker rm <nome_container>`: Elimina un container.
- `docker run --rm <immagine>`: Esegue un container e lo elimina automaticamente al termine.
- `docker ps`: Mostra i container in esecuzione.
- `docker ps -a`: Mostra tutti i container, compresi quelli non in esecuzione.
- `docker stop <nome_container>`: Ferma un container in esecuzione.
- `docker run -d <immagine>`: Esegue un container in modalità detached.

Questi punti e comandi forniscono una panoramica utile per gestire i container Docker e comprendere il loro comportamento.
## References

- [[Eseguire un Container]]