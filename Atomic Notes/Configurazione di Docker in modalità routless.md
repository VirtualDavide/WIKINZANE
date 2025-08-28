2025-03-23 20:58

Tags : [[Docker]]

# Configurazione di Docker in modalità routless

Impostare Docker in modalità rootless significa eseguire il demone Docker e i contenitori senza privilegi di root, migliorando così la sicurezza. Ecco come puoi configurare Docker in modalità rootless:

### 1. Requisiti

Assicurati di avere i seguenti requisiti:

- Una distribuzione Linux supportata (ad esempio, Ubuntu, Fedora, Debian).
- Docker installato. Se non lo hai già installato, puoi seguire le istruzioni ufficiali di installazione di Docker.

### 2. Installare Docker in modalità rootless

Puoi installare Docker in modalità rootless seguendo questi passaggi:

#### Passo 1: Installare le dipendenze

Assicurati di avere installato `uidmap`, che è necessario per la modalità rootless. Puoi installarlo con il seguente comando:

```bash
sudo apt-get install uidmap
```

#### Passo 2: Scaricare lo script di installazione

Puoi utilizzare lo script di installazione di Docker per la modalità rootless. Esegui il seguente comando:

```bash
curl -fsSL https://get.docker.com/rootless | sh
```

Questo script installerà Docker nella tua home directory.

#### Passo 3: Aggiungere il percorso di Docker al tuo PATH

Dopo l'installazione, dovrai aggiungere il percorso di Docker al tuo `PATH`. Puoi farlo aggiungendo la seguente riga al tuo file `~/.bashrc` o `~/.bash_profile`:

```bash
export PATH=$HOME/bin:$PATH
```

Dopo aver modificato il file, esegui:

```bash
source ~/.bashrc
```

#### Passo 4: Avviare il demone Docker in modalità rootless

Puoi avviare il demone Docker in modalità rootless con il seguente comando:

```bash
dockerd-rootless.sh
```

Puoi anche eseguire questo comando in background aggiungendo `&` alla fine:

```bash
dockerd-rootless.sh &
```

### 3. Eseguire Docker in modalità rootless

Ora puoi eseguire i comandi Docker normalmente. Ad esempio, per eseguire un contenitore Nginx, puoi usare:

```bash
docker run -d -p 80:80 nginx
```


## References

- [[Installazione Docker]]
- [[Cercare,scaricare ed eseguire un'immagine]]