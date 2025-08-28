2024-12-21 17:51

Tags :

# VirtualBox Guest-Additions


Nella sezione *generale* o nelle impostazione nella sezione *cartelle condivise*, è possibile attivare funzionalità come la copia degli appunti da un sistema ad un altro, o la possibilità di condividere una cartella tra il nostro sistema operativo principale e quello virtualizzato.

### Installazione (*macchina virtuale linux*)

**Installazione sulla macchina (*Debian-like*)**

```bash
sudo apt update
sudo apt install build-essential
```

*riavviare il sistema dopo l'installazione...*

- **Avvia la macchina virtuale**:
    - Apri VirtualBox e avvia la macchina virtuale in cui desideri installare le Guest Additions.
- **Accedi alla macchina virtuale**:
    - Una volta avviata, accedi al sistema operativo della macchina virtuale.
- **Inserisci il CD delle Guest Additions**:
    - Nella barra dei menu di VirtualBox, vai su `Dispositivi` > `Inserisci immagine CD delle Guest Additions...`.
    - Questo monterà un'immagine ISO contenente le Guest Additions all'interno della macchina virtuale.

*riavviare il sistema dopo l'installazione...*
## References

- [[VirtualBox]]