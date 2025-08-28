2025-04-04 21:59

Tags : [[Docker]]

# Build, push ed import di un DockerFile

Certo! Ecco una guida passo-passo su come costruire un'immagine Docker, fare il push su Docker Hub, salvare l'immagine su una pennetta USB e importarla su un altro dispositivo.

### 1. Costruire l'immagine Docker

Assicurati di essere nella directory in cui si trova il tuo Dockerfile e utilizza il seguente comando per costruire l'immagine:

```bash
docker build -t nome_utente/nome_immagine:tag .
```

Sostituisci `nome_utente` con il tuo nome utente Docker Hub, `nome_immagine` con il nome che desideri dare all'immagine e `tag` con una versione (ad esempio, `latest`).

Esempio:

```bash
docker build -t tuo_nome_utente/qtdemo:latest .
```

### 2. Accedi a Docker Hub

Se non hai già effettuato l'accesso a Docker Hub, usa il comando:

```bash
docker login
```

Ti verrà chiesto di inserire il tuo nome utente e la tua password.

### 3. Eseguire il push dell'immagine su Docker Hub

Dopo aver costruito l'immagine e aver effettuato l'accesso, puoi eseguire il push dell'immagine su Docker Hub con il seguente comando:

```bash
docker push nome_utente/nome_immagine:tag
```

Esempio:

```bash
docker push tuo_nome_utente/qtdemo:latest
```

### 4. Salvare l'immagine su una pennetta USB

Per salvare l'immagine Docker su una pennetta USB, prima devi esportare l'immagine in un file tar. Usa il comando `docker save`:

```bash
docker save -o nome_immagine.tar nome_utente/nome_immagine:tag
```

Esempio:

```bash
docker save -o qtdemo.tar tuo_nome_utente/qtdemo:latest
```

Ora puoi copiare il file `qtdemo.tar` sulla tua pennetta USB. Assicurati che la pennetta sia montata e utilizza il comando `cp` per copiare il file:

```bash
cp qtdemo.tar /percorso/della/pennetta/
```

Sostituisci `/percorso/della/pennetta/` con il percorso effettivo della tua pennetta USB.

### 5. Importare l'immagine su un altro dispositivo

Collega la pennetta USB al secondo dispositivo e assicurati che sia montata. Poi, utilizza il comando `docker load` per importare l'immagine dal file tar:

```bash
docker load -i /percorso/della/pennetta/qtdemo.tar
```

Sostituisci `/percorso/della/pennetta/qtdemo.tar` con il percorso effettivo del file tar sulla tua pennetta.

### 6. Verificare l'importazione

Dopo aver importato l'immagine, puoi verificare che sia stata caricata correttamente utilizzando il comando:

```bash
docker images
```

Dovresti vedere l'immagine `tuo_nome_utente/qtdemo` nell'elenco delle immagini disponibili.

### 7. Eseguire l'immagine

Infine, puoi eseguire l'immagine importata con il comando:

```bash
docker run -ti -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --ipc=host --net=host tuo_nome_utente/qtdemo:latest
```

### Riepilogo dei comandi

Ecco un riepilogo dei comandi che hai utilizzato:

```bash
# Costruire l'immagine
docker build -t tuo_nome_utente/qtdemo:latest .

# Accedere a Docker Hub
docker login

# Eseguire il push dell'immagine
docker push tuo_nome_utente/qtdemo:latest

# Salvare l'immagine su un file tar
docker save -o qtdemo.tar tuo_nome_utente/qtdemo:latest

# Copiare il file tar sulla pennetta USB
cp qtdemo.tar /percorso/della/pennetta/

# Importare l'immagine su un altro dispositivo
docker load -i /percorso/della/pennetta/qtdemo.tar

# Verificare l'importazione
docker images

# Eseguire l'immagine
docker run -ti -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --ipc=host --net=host tuo_nome_utente/qtdemo:latest
```

Seguendo questi passaggi, dovresti essere in grado di costruire, caricare, salvare e importare un'immagine Docker senza problemi. Se hai ulteriori domande o hai
## References

- [[Come scrivere un DockerFile]]
- [[DockerFile e ContainerFile]]