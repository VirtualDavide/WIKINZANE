2025-03-21 12:47

Tags : [[DailyLinux]]

# GitHub
![[github-mark-white 1.png]]
### Cos'è GitHub
GitHub è una piattaforma di hosting per repository Git che consente agli sviluppatori di collaborare e gestire progetti di sviluppo software. È uno strumento molto popolare nel mondo della programmazione e offre una serie di funzionalità che facilitano la collaborazione tra team e la gestione del codice sorgente. Ecco alcune delle caratteristiche principali di GitHub:

1. **Hosting di Repository**: GitHub consente di ospitare repository Git, sia pubblici che privati. I repository pubblici sono accessibili a chiunque, mentre i repository privati sono visibili solo ai collaboratori autorizzati.

2. **Interfaccia Web**: GitHub fornisce un'interfaccia web intuitiva che consente di visualizzare, modificare e gestire i file del progetto, oltre a visualizzare la cronologia delle commit e le pull request.

3. **Collaborazione**: Gli sviluppatori possono collaborare facilmente su progetti, segnalare problemi (issues), e discutere le modifiche attraverso le pull request. Le pull request consentono di proporre modifiche a un progetto e di discuterle prima di integrarle nel ramo principale.

4. **Integrazione Continua**: GitHub supporta strumenti di integrazione continua (CI) che automatizzano il processo di test e distribuzione del codice, migliorando la qualità del software.

5. **Documentazione**: GitHub consente di creare documentazione direttamente all'interno del repository, utilizzando file README e wiki.

### Come Fare il Push del Tuo Progetto Online su GitHub

Dopo aver creato un repository su GitHub e aver configurato il tuo progetto localmente, puoi eseguire il push del tuo progetto online seguendo questi passaggi:

#### Passo 1: Creare un Repository su GitHub

1. **Accedi a GitHub**: Vai su [github.com](https://github.com/) e accedi al tuo account. Se non hai un account, puoi crearne uno gratuitamente.

2. **Crea un Nuovo Repository**:
   - Clicca sul pulsante "+" in alto a destra e seleziona "New repository".
   - Dai un nome al tuo repository (ad esempio, "nome-del-progetto").
   - Puoi aggiungere una descrizione, scegliere se il repository sarà pubblico o privato e decidere se inizializzarlo con un README (se lo fai, dovrai gestire il conflitto in seguito).
   - Clicca su "Create repository".

#### Passo 2: Collegare il Repository Locale a GitHub

1. **Copia l'URL del Repository**: Dopo aver creato il repository su GitHub, vedrai un URL (può essere HTTPS o SSH). Copialo.

2. **Collegare il Tuo Repository Locale a Quello Remoto**:
   Apri il terminale nella directory del tuo progetto e utilizza il seguente comando per collegare il tuo repository locale a quello remoto:
   ```bash
git remote add origin https://github.com/tuo-username/nome-del-progetto.git
   ```
   Sostituisci `tuo-username` e `nome-del-progetto` con il tuo nome utente GitHub e il nome del tuo repository.

#### Passo 3: Eseguire il Push del Progetto

1. **Invia i Tuoi Commit al Repository Remoto**:
   Dopo aver collegato il repository locale a quello remoto, puoi eseguire il push delle tue modifiche. Usa il seguente comando:
   ```bash
git push -u origin master
   ```
   Se stai usando una versione più recente di Git, il ramo principale potrebbe essere chiamato `main` invece di `master`. In tal caso, usa:
   ```bash
git push -u origin main
   ```

2. **Autenticazione**: Se stai utilizzando HTTPS, potrebbe essere necessario inserire le tue credenziali GitHub (nome utente e password o token di accesso personale) per completare il push.

#### Passo 4: Verifica su GitHub

Dopo aver eseguito il push, vai al tuo repository su GitHub e verifica che i file siano stati caricati correttamente. Dovresti vedere la cronologia delle commit e i file del tuo progetto.
## References

- [[Git]]
- [[GitHub - helpers]]