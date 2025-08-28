2025-08-21 09:28

Tags : [[DailyLinux]]

# AppImage

**AppImage** è un formato per la distribuzione di software portabile su Linux senza la necessità di autorizzazioni di *superutente* per installare l'applicazione. **Ha come scopo la distribuzione di software binario indipendente dalla distribuzione Linux per gli sviluppatori di applicazioni**. Rilasciato la prima volta nel 2004 con il nome *klik*, è stato continuamente sviluppato, poi rinominato nel 2011 in *PortableLinuxApps* e successivamente nel 2013 in **AppImage**.

AppImage mira a essere un sistema di distribuzione di applicazioni per Linux con i seguenti obiettivi : 

- *semplicità*
- *compatibilità binaria
- *nessuna installazione
- *nessun permesso di root
- *portabile
- *mantenere il sistema intatto*

AppImage non installa l'applicazione nel senso tradizionale di Linux. Invece di inserire i vari file dell'applicazione nelle posizioni appropriate della distribuzione nel file system, il file AppImage è solo l'immagine compressa dell'applicazione. Utilizza un solo file per applicazione. Ogni file è autonomo, include **tutte le librerie da cui dipende** l'applicazione che non fanno già parte del sistema di base di destinazione.

Gli utenti regolari delle comuni distribuzioni Linux possono scaricarlo, renderlo eseguibile ed eseguirlo.
## References

- [[AppImage - creazione di un AppImage]]