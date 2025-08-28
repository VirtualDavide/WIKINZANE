2025-01-14 16:46

Tags : [[ServerSideDevelopment]] - [[Java]]

# Tomcat
![[Pasted image 20250116205401.png]]

**Apache Tomcat** (o semplicemente **Tomcat**) è un [server web](https://it.wikipedia.org/wiki/Server_web "Server web") (nella forma di [contenitore servlet](https://it.wikipedia.org/wiki/Servlet "Servlet")) [open source](https://it.wikipedia.org/wiki/Open_source "Open source") sviluppato dalla [Apache Software Foundation](https://it.wikipedia.org/wiki/Apache_Software_Foundation "Apache Software Foundation"). Implementa le specifiche [JavaServer Pages](https://it.wikipedia.org/wiki/JavaServer_Pages "JavaServer Pages") (JSP) e [servlet](https://it.wikipedia.org/wiki/Servlet "Servlet"), fornendo quindi una [piattaforma software](https://it.wikipedia.org/wiki/Piattaforma_(informatica) "Piattaforma (informatica)") per l'[esecuzione](https://it.wikipedia.org/wiki/Esecuzione_(informatica) "Esecuzione (informatica)") di [applicazioni web](https://it.wikipedia.org/wiki/Applicazione_web "Applicazione web") sviluppate in linguaggio [Java](https://it.wikipedia.org/wiki/Java_(linguaggio_di_programmazione) "Java (linguaggio di programmazione)"). La sua [distribuzione](https://it.wikipedia.org/wiki/Distribuzione_(software) "Distribuzione (software)") standard include anche le funzionalità di web server tradizionale, che corrispondono al prodotto [Apache](https://it.wikipedia.org/wiki/Apache_HTTP_Server "Apache HTTP Server").

In passato, Tomcat era gestito nel contesto del [Jakarta Project](https://it.wikipedia.org/wiki/Jakarta_Project "Jakarta Project"), ed era pertanto identificato con il nome di **Jakarta Tomcat**; attualmente è oggetto di un progetto indipendente. Tomcat è distribuito sotto la [Licenza Apache](https://it.wikipedia.org/wiki/Licenza_Apache "Licenza Apache"), ed è scritto interamente in [Java](https://it.wikipedia.org/wiki/Java_(linguaggio_di_programmazione) "Java (linguaggio di programmazione)"); può quindi essere eseguito su qualsiasi architettura su cui sia installata una [JVM](https://it.wikipedia.org/wiki/Macchina_virtuale_Java "Macchina virtuale Java").

## Installazione (Debian-like)

*Aggiornare il sistema prima di scaricare qualsiasi applicativo :* 
```bash
sudo apt update
sudo apt upgrade
```

**Passo 1** : *Installare la Java Virtual Machine*
```bash
sudo apt intall openjdj-21-jdk 
```
*verificare l'installazione di JVM con il comando* : 
```bash
java -version
```

**Passo 2** : scaricare Apache Tomcat (*scaricarlo per default nella cartella `opt`*)
```bash
cd /opt
sudo wget https://downloads.apache.org/tomcat/tomcat-11/v11.0.2/bin/apache-tomcat-11.0.2.tar.gz
```

**Passo 3** : Estrarre il file (*rinominare anche la cartella per comodità*)
```bash
sudo tar xzf apache-tomcat.11.0.2.tar.gz
sudo mv apache-tomcat-11.0.2.tar.gz tomcat-11.0.2
```

**Passo 4** : Configurare i permessi (*ci assicuriamo che l'utente che esegua tomcat abbia i permessi corretti*)
```bash
sudo chown -R giancarlo:giancarlo /opt/tomcat-11.0.2
```

**Passo 5** : *Avviare Tomcat*
```bash
/opt/tomcat/bin/startup.sh
```

**Passo 6** : *Verificare l'installazione* (aprire qualsiasi browser)
```
http:localhost:8080
```

## References

- [[Servlet]]
- [[Sviluppo di un Demone (tomcat)]]