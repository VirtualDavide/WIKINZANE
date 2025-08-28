2024-12-30 21:32

Tags : [[Architettura del sistema]] / [[101.1]]

# D-bus, Hal e Udev

D-bus (*message bus system*) fornisce una canale di comunicazione alle applicazioni l'una all'altra. (*esempio : programma della stampante e software di stampa* )

Fornisce un demone di sistema per eventi come "un nuovo harware è stato collegato" o "la coda di stampa è cambiata" e un demone per user-login-session per far comunicare le applicazioni in usurspace.

D-bus si collega a (*precedentemente HAL (hardware abstract layer) deprecato poi nel 2010 da udev*) udev e fornisce un database aggiornato in tempo reale sulle periferiche collegate al computer. 

Il suo scopo è fornire alle applicazioni una API semplice, portabile e astratta. Indipendentemente dall'hardware di appoggio.

Quando udev rileva un cambiamento nel sistema (ad esempio, un dispositivo hardware che viene collegato), può inviare notifiche tramite D-Bus. Questo permette ad altre applicazioni di essere informate immediatamente riguardo a questi eventi.

![[Pasted image 20241230213839.png]]

Ecco alcuni esempi pratici di come D-Bus viene utilizzato:

1. **Stampa**: Quando un documento viene inviato a una stampante, il software di stampa può utilizzare D-Bus per comunicare con il demone della stampante. Ad esempio, il software di stampa può inviare un messaggio per avviare la stampa, mentre il demone della stampante può inviare notifiche sullo stato della stampa (ad esempio, "stampa completata" o "errore nella stampante").
    
2. **Gestione dell'alimentazione**: Un'applicazione di gestione dell'alimentazione può utilizzare D-Bus per ricevere notifiche quando il computer entra in modalità sospensione o ibernazione. Al contempo, altre applicazioni possono registrarsi per ricevere eventi relativi alla gestione dell'alimentazione, come la modifica dello stato della batteria.
    
3. **Gestione delle periferiche**: Quando un nuovo dispositivo USB viene collegato al computer, il demone di sistema D-Bus può inviare un messaggio a tutte le applicazioni registrate per informarle che un nuovo hardware è stato rilevato. Ad esempio, un'applicazione di gestione file potrebbe aggiornare la sua interfaccia utente per mostrare il nuovo dispositivo.
    
4. **Notifiche di sistema**: Le applicazioni possono utilizzare D-Bus per inviare notifiche al sistema. Ad esempio, un'applicazione di messaggistica può inviare una notifica quando riceve un nuovo messaggio, e il sistema operativo può visualizzare un avviso all'utente.
    
5. **Controllo multimediale**: Un lettore musicale può utilizzare D-Bus per comunicare con un'interfaccia utente o un'applicazione di controllo remoto. Ad esempio, quando l'utente preme "play" su un telecomando, il comando può essere inviato tramite D-Bus al lettore musicale per avviare la riproduzione.
    

In sintesi, D-Bus fornisce un meccanismo flessibile e potente per la comunicazione tra applicazioni, semplificando l'interazione tra diversi componenti software e hardware nel sistema.
## References

- [[Runlevel e Demoni]]