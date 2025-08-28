2025-04-03 23:18

Tags : [[Docker]]

# Elencare, ispezionare e rimuovere volumi

Docker offre la possibilità di creare volumi persistenti che possono essere associati a uno o più container. **I volumi sono entità a sé stanti che possono esistere indipendentemente dai container e sono utilizzati per mantenere i dati persistenti anche dopo l'eliminazione di un container.**

Per creare un volume, si utilizza il comando `docker volume create`. Se eseguito senza argomenti, questo comando genera un volume **anonimo**, il cui nome viene assegnato automaticamente da Docker. Se si desidera creare un volume con un nome specifico, è sufficiente aggiungere il nome al comando. Ad esempio:

```bash
docker volume create my_volume
```

Questo comando crea un volume chiamato `my_volume`. Non ci sono limiti predefiniti alla dimensione del volume; esso cresce in base ai dati che vi vengono scritti, **a meno che non vengano implementati limiti di quota.**

Per elencare tutti i volumi presenti nel sistema, si utilizza il comando:

```bash
docker volume ls
```

Questo comando mostrerà tutti i volumi, inclusi quelli anonimi creati automaticamente all'avvio di un container. I volumi possono esistere anche se non sono attualmente associati a un container, il che significa che è possibile avere volumi non più in uso.

Se si desidera rimuovere i volumi non più utilizzati da alcun container, si può utilizzare il comando:

```bash
docker volume prune
```

Questo comando rimuoverà tutti i volumi locali (*anonimi : -a per tutti i volumi non utilizzati*) che non sono utilizzati da almeno un container. È importante essere sicuri di voler procedere, poiché questa operazione non può essere annullata.

Per ispezionare un volume e ottenere dettagli come il punto di montaggio, si può utilizzare il comando:

```bash
docker volume inspect my_volume
```

Questo comando fornisce informazioni dettagliate sul volume, inclusa la data di creazione e il percorso di montaggio. Ad esempio, l'output potrebbe includere:

```json
[
    {
        "CreatedAt": "2023-10-01T12:00:00Z",
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/my_volume/_data",
        "Name": "my_volume",
        "Options": {},
        "Scope": "local"
    }
]
```

Se si desidera vedere quali container utilizzano un determinato volume, è possibile utilizzare il comando:

```bash
docker ps
```

Questo comando elenca tutti i container attivi. Per ogni container, è possibile utilizzare il comando `docker inspect` per ottenere informazioni dettagliate, inclusi i volumi montati. Ad esempio:

```bash
docker inspect <container_id>
```

Nell'output del comando, se il conteiner utilizza uno dei volumi presenti, sarà presente sotto le voci `mounts` o `volumes`. È interessante notare che non è il volume a sapere quale container lo sta utilizzando, ma sono gli stessi conteiner che conservano questa informazione.

Infine, è importante notare che il percorso fisico dei volumi varia a seconda di come Docker è stato installato e dell'utente che lo esegue. Ad esempio, se Docker è eseguito come utente normale, i volumi possono trovarsi in:

```
/home/<username>/.local/share/docker/volumes/
```

Se Docker è eseguito come root, i volumi si troveranno in:

```
/var/lib/docker/volumes/
```

In caso di utilizzo di Podman, i volumi si troveranno in un percorso simile, ma all'interno della home dell'utente.
## References

- [[Volumi vs Bind mounts]]