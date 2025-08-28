2025-03-21 12:39

Tags : [[DailyLinux]]

# Git

![[Pasted image 20250321125111.png]]

Git è un sistema di controllo versione distribuito, progettato per gestire progetti di sviluppo software in modo efficiente. Creato da Linus Torvalds nel 2005, Git consente a più sviluppatori di lavorare contemporaneamente su un progetto, tenendo traccia delle modifiche apportate al codice sorgente nel tempo. GitHub, d'altra parte, è una piattaforma di hosting per repository Git che facilita la collaborazione tra sviluppatori, offrendo un'interfaccia web e funzionalità aggiuntive come la gestione delle pull request e l'integrazione continua.
### Le Tre Aree di Git

Git gestisce il codice sorgente attraverso tre aree principali:

1. **Working Directory**: Questa è la cartella locale in cui lavori. Contiene i file del tuo progetto e le modifiche che hai apportato. Quando modifichi un file, stai lavorando nella tua working directory.
    
2. **Staging Area**: Questa area è un'area intermedia in cui puoi preparare le modifiche prima di effettuare un commit. Quando esegui il comando `git add`, stai spostando i file dalla working directory alla staging area. Qui puoi selezionare quali modifiche includere nel prossimo commit.
    
3. **Repository**: Questa è la zona in cui Git memorizza la cronologia delle modifiche. Ogni volta che effettui un commit, Git crea uno snapshot del progetto e lo memorizza nel repository. Il repository può essere locale (sul tuo computer) o remoto (su un server come GitHub).

### Inizializzazione di un Progetto su Git e GitHub

Per inizializzare un progetto su Git e GitHub, segui questi passaggi:

**Installare Git**: Scarica e installa Git dal sito ufficiale [git-scm.com](https://git-scm.com/).
    
**Creare un Nuovo Progetto Locale**:
Apri il terminale e naviga nella directory desiderata e crea una nuova cartella per il tuo progetto e inizializza un repository Git:
```bash
mkdir nome-del-progetto
cd nome-del-progetto
git init
```

**Aggiungere File al Progetto**: Crea o aggiungi file al tuo progetto e aggiungili alla staging area:
```bash
echo "# Nome del Progetto" > README.md
git add .
```

**Effettuare il primo commit:** 
```bash
git commit -m "Primo commit"
```

### Gestione degli Snapshot
In Git, gli snapshot rappresentano lo stato di un progetto in un determinato momento. Quando effettui un commit, Git crea un'immagine completa del progetto. Utilizza una struttura di dati chiamata "albero" per rappresentare gli snapshot, memorizzando solo i riferimenti ai file modificati per ottimizzare lo spazio.

Per visualizzare l'albero delle commit, utilizza il comando `git log`. Per una rappresentazione grafica chiara, puoi eseguire:

```bash
git log --graph --oneline --decorate
```


### Configurazione di Nome ed Email
Per configurare il tuo nome e la tua email in Git, utilizza i seguenti comandi:
```bash
git config --global user.name "Il Tuo Nome"
git config --global user.email "tuo@email.com"
```

Puoi verificare la configurazione con:
```bash
git config --global --list
```
## References

- [[GitHub]]
- [[GitHub - helpers]]