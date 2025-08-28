2024-12-31 14:18

Tags : [[Architettura del sistema]] / [[101.2]]

# Runlevel

Un runlevel definisce lo stato di un sistema operativo Linux o Unix. o runlevel rappresentano i diversi livelli di operatività del sistema, ognuno dei quali attiva o disattiva specifici servizi o processi (*i runlevel sono generalmente usati nei sistemi che utilizzano system V*).

I runlevel sono numerati da 0 a 6 e hanno i seguenti significati : 

- **Runlevel 0** : Arresto del sistema, viene utilizzato per spegnere il PC in modo sicuro.
- **Runlevel 1** : Modalità di emergenza (*single mode user*) In questo stato, il sistema avvia solo i servizi essenziali e consente l'accesso solo a un singolo utente (di solito l'amministratore). È utile per la manutenzione e la risoluzione dei problemi.
- **Runlevel 2**: Modalità multi-utente senza supporto per la rete. In questo runlevel, il sistema consente l'accesso a più utenti, ma senza servizi di rete attivi.
- **Runlevel 3**: Modalità multi-utente con supporto per la rete. Questo è un runlevel comune per i server, in cui gli utenti possono accedere al sistema e i servizi di rete sono attivi ( interfaccia grafica non attiva ).
- **Runlevel 4**: Non utilizzato o riservato per scopi personalizzati. In molte distribuzioni, questo runlevel non ha uno scopo definito e può essere utilizzato per configurazioni personalizzate.
- **Runlevel 5**: Modalità grafica multi-utente. In questo runlevel, il sistema avvia un ambiente desktop grafico, consentendo agli utenti di interagire con il sistema tramite un'interfaccia grafica.
- **Runlevel 6**: Riavvio del sistema (reboot). Questo runlevel viene utilizzato per riavviare il computer.

Tramite il comandi `runlevel` o `who -r`, possiamo vedere sul nostro sistema linux, quale runlevel è attivato.

Quando il sistema si avvia, il bootloader carica il kernel e il kernel avvia il processo di init (o un sistema di inizializzazione alternativo come systemd). Il processo di init determina il runlevel da avviare e carica i servizi e i processi appropriati in base a quel runlevel.
## References

- [[Init del SO]]
- [[Runlevel e la diagnostica al boot]]