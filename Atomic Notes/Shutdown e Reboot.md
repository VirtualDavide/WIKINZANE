2025-01-03 13:30

Tags : [[Architettura del sistema]] / [[101.3]]

# Shutdown e Reboot

Possiamo utilizzare `telinit` per cambiare runlevel e spegnere la macchina o riavviare immediatamente il sistema, tutta via in questo modo, i processi possono essere terminati non correttamente e gli utenti collegati possono perdere il lavoro svolto.

È preferibile utilizzare il comando `shutdown` che prima invia un messaggio broadcast a tutti gli utenti collegati avvertendoli che il sistema sta per spegnersi. 

Poi dice ad init di cambiare runlevel.

Questo prima di farlo, manda un messaggio di `SIGTERM` dove invita tutti i processi in esecuzione a terminarsi correttamente, se entro un tempo di 5 secondi questi non terminano (*il tempo può essere anche stabilito con l'opzione `-t`*), il processo di init uccide tutti i processi bloccati con un segnale di `SIGKILL` per evitare stalli.

Alcuni comandi utili possono essere :

```bash
shutdown 5 "Il sistema verrà spento fra 5 minuti"
```

Indichiamo alla macchina che deve spegnersi fra 5 minuti, inviando a tutti gli utenti un messaggio broadcast personalizzato, in questo caso "*Il sistema verrà spento fra 5 minuti*".

```bash
shutdown -r
```

Riavvia la macchina.

```bash
shutdown -h
```

Ferma la macchina, interrompendo tutti i processi, ma senza spegnarla.

```bash
shutdown 17:05
```

Spegnimento programmato per le 17:05.

```bash
shutdown -c
```

Cancelliamo l'ultimo spegnimento programmato.

Il messaggio di broadcast comunque verrà inviato solo 15 minuti prima dello spegnimento programmato, quindi se si vuole inviare un messaggio brodcast in qualsiasi momento a tutti gli utenti collegati, si può utilizzare il comando `wall` : 

```bash
wall "Ciao questo è un messaggio broadcast per tutti $(date)"
```

(*non usare punti esclamativi*)
## References

- [[Runlevel]]