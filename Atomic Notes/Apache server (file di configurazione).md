2025-01-13 21:45

Tags : [[[[DailyLinux]]]]

# Apache server (file di configurazione)

In `/etc/apache2/`. Ecco una breve descrizione delle cartelle e dei file che hai elencato:

- **apache2.conf**: Questo è il file di configurazione principale di Apache. Contiene le impostazioni globali per il server web.
    
- **conf-enabled/**: Questa cartella contiene i file di configurazione che sono abilitati. I file qui presenti sono collegamenti simbolici ai file nella cartella `conf-available/`.
    
- **conf-available/**: Qui puoi trovare i file di configurazione disponibili per Apache. Puoi abilitare o disabilitare questi file utilizzando i comandi `a2enconf` e `a2disconf`.
    
- **magic**: Questo file è utilizzato per determinare il tipo di contenuto dei file in base al loro contenuto, piuttosto che all'estensione.
    
- **mods-enabled/**: Contiene i moduli di Apache che sono attualmente abilitati. Anche in questo caso, i file qui presenti sono collegamenti simbolici ai file nella cartella `mods-available/`.
    
- **mods-available/**: Qui puoi trovare i moduli disponibili per Apache. Puoi abilitare o disabilitare questi moduli utilizzando i comandi `a2enmod` e `a2dismod`.
    
- **ports.conf**: Questo file specifica le porte su cui Apache ascolta le richieste. Di solito, include la configurazione per la porta 80 (HTTP) e la porta 443 (HTTPS).
    
- **sites-available/**: Contiene i file di configurazione per i vari siti web che puoi ospitare sul tuo server Apache.
    
- **sites-enabled/**: Questa cartella contiene i file di configurazione dei siti che sono attualmente abilitati. I file qui presenti sono collegamenti simbolici ai file nella cartella `sites-available/`.

## References

- [[Apache server]]