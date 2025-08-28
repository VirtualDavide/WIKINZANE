2025-01-16 21:09

Tags : [[DailyLinux]] 

# Sviluppo di un Demone (tomcat)

Scrivere un demone (o servizio) su Linux implica la creazione di un file di unità per `systemd`, che è il sistema di init e gestore di servizi utilizzato dalla maggior parte delle distribuzioni Linux moderne, inclusi Ubuntu e CentOS. 

### Struttura di un file di unità di systemd

Un file di unità di `systemd` è composto da diverse sezioni, ognuna delle quali ha uno scopo specifico. 

**Sezione** `[Unit]`: 
Questa sezione contiene informazioni generali sul servizio.
- **Description**: Fornisce una breve descrizione del servizio.
- **After**: Specifica che il servizio deve essere avviato dopo un altro servizio (in questo caso, `network.target`, che indica che la rete deve essere attiva prima di avviare Tomcat).

**Sezione** `[Service]`: 
Questa sezione definisce come il servizio deve essere eseguito:
- **Type**: Indica il tipo di servizio. `simple` significa che il servizio viene considerato attivo non appena il processo avviato dal comando `ExecStart` è in esecuzione.

	- **simple**: Questo è il tipo più comune. Indica che il servizio è considerato attivo non appena il processo avviato dal comando `ExecStart` è in esecuzione. Non ci si aspetta che il processo crei ulteriori processi figlio.   
	
	- **forking**: Utilizzato per i servizi che si avviano in modo "forking", ovvero che creano un processo figlio e terminano il processo padre. `systemd` considera il servizio attivo quando il processo padre termina.   
	- **oneshot**: Utilizzato per i servizi che eseguono un'azione e poi terminano. È utile per script di inizializzazione o configurazione. `systemd` attende che il processo termini prima di considerare il servizio attivo.
	
	- **notify**: Utilizzato per i servizi che inviano un messaggio a `systemd` per segnalare che sono pronti. Questo è utile per i servizi che richiedono tempo per avviarsi e vogliono informare `systemd` quando sono pronti.
	
	- **dbus**: Utilizzato per i servizi che si registrano su D-Bus. `systemd` considera il servizio attivo quando il servizio si registra correttamente su D-Bus.
	
	- **idle**: Indica che il servizio deve essere avviato solo quando il sistema è inattivo. Questo è utile per i servizi che non devono interferire con altre operazioni.
	
- **User**: Specifica l'utente sotto il quale il servizio deve essere eseguito. È importante per la sicurezza, poiché eseguire servizi come root può essere rischioso.

- **Group**: Specifica il gruppo sotto il quale il servizio deve essere eseguito.

- **Environment**: Qui puoi definire variabili d'ambiente necessarie per il servizio. Ad esempio, `JAVA_HOME` indica la posizione dell'installazione di Java, mentre `CATALINA_HOME` e `CATALINA_BASE` indicano le directory di installazione di Tomcat.

- **ExecStart**: Il comando da eseguire per avviare il servizio. In questo caso, è lo script `startup.sh` di Tomcat.

- **ExecStop**: Il comando da eseguire per fermare il servizio. Qui è lo script `shutdown.sh` di Tomcat.

**Sezione** `[Install]`:
La sezione `[Install]` di un file di unità di `systemd` è fondamentale per definire come e quando il servizio deve essere avviato.
- **WantedBy**: Specifica in quale target il servizio deve essere avviato. `multi-user.target` è un target comune per i servizi di sistema che devono essere avviati in modalità multi-utente.

- **RequiredBy**: Simile a `WantedBy`, ma indica che il servizio è una dipendenza necessaria per il target specificato. Se il servizio non può essere avviato, il target non verrà avviato.

- **Alias**: Puoi definire alias per il servizio, che possono essere utilizzati per riferirsi al servizio in modo alternativo.

## Esempio di Demone (tomcat)

```bash
[Unit]
Description=Apache Tomcat Web Application Container
After=network.target

[Service]
Type=simple
User=giancarlo
Group=giancarlo
Environment=JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
Environment=CATALINA_HOME=/opt/tomcat
Environment=CATALINA_BASE=/opt/tomcat
ExecStart=/opt/tomcat/bin/startup.sh
ExecStop=/opt/tomcat/bin/shutdown.sh

[Install]
WantedBy=multi-user.target
```

Salva e chiudi il file. Poi, abilita e avvia il servizio:
```bash
sudo systemctl daemon-reload
sudo systemctl enable tomcat
sudo systemctl start tomcat
```

La directory `/etc/systemd/system/` è il luogo standard in cui vengono memorizzati i file di unità di `systemd` per i servizi di sistema personalizzati e per i servizi installati manualmente.
## References

- [[Runlevel e Demoni]]
- [[Init del SO]]
- [[Tomcat]]