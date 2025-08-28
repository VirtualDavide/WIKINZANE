2025-04-04 16:47

Tags : [[Docker]]

# DockerFile e ContainerFile

Un Dockerfile è un file di testo che c**ontiene una serie di istruzioni e comandi utilizzati per automatizzare la creazione di un'immagine Docker.** Le immagini Docker sono utilizzate per creare container, che sono ambienti isolati in cui è possibile eseguire applicazioni.

1. **Struttura del Dockerfile**: Un Dockerfile è un file di testo che contiene una serie di istruzioni per costruire un'immagine Docker. Ogni istruzione nel Dockerfile crea un nuovo layer nell'immagine finale.

2. **Layering**: Ogni comando nel Dockerfile genera un nuovo layer. Questo significa che più istruzioni possono aumentare la dimensione dell'immagine. È importante combinare i comandi quando possibile per ridurre il numero di layer e, di conseguenza, la dimensione dell'immagine.

3. **Cache di Docker**: Durante la costruzione dell'immagine, Docker utilizza una cache per ottimizzare il processo. Se un'istruzione non è cambiata rispetto a una costruzione precedente, Docker riutilizza il layer esistente invece di ricostruirlo. Questo può portare a problemi se si scaricano risorse che possono cambiare nel tempo, poiché si potrebbe ottenere una versione obsoleta.

4. **Comandi principali**:
   - `FROM`: Specifica l'immagine di base da cui partire.
   - `RUN`: Esegue comandi all'interno del container durante la costruzione dell'immagine.
   - `COPY`: Copia file o directory dal filesystem locale all'interno del container.
   - `ADD`: Simile a `COPY`, ma può anche scaricare file da URL.
   - `CMD`: Definisce il comando predefinito da eseguire quando si avvia il container.
   - `ENTRYPOINT`: Imposta l'eseguibile predefinito che viene eseguito quando si avvia il container.
   - `ENV`: Imposta variabili d'ambiente che saranno disponibili nel container.
   - `EXPOSE`: Indica che il container ascolta su una certa porta.

5. **Variabili d'ambiente**: Le variabili d'ambiente impostate con `ENV` sono persistenti e disponibili in tutte le esecuzioni del container, a differenza delle variabili impostate temporaneamente in un comando `RUN`.

6. **Contesto di costruzione**: Quando si costruisce un'immagine, il contesto di costruzione è la directory in cui si trova il Dockerfile e tutti i file necessari per la costruzione dell'immagine. Solo i file all'interno di questo contesto possono essere copiati nel container.

7. **Comportamento delle istruzioni**: È importante notare che tra un'istruzione e l'altra, il container viene "spento" e "riacceso". Questo significa che non c'è continuità tra le istruzioni, e le variabili d'ambiente impostate in un'istruzione non saranno disponibili nelle istruzioni successive.
## References

- [[Come scrivere un DockerFile]]
- [[Build, push ed import di un DockerFile]]