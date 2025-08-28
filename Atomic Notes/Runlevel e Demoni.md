2025-01-02 15:40

Tags : [[Linux LPI - 101]]

## Runlevel Sys V

Con Sys V init per modificare i demoni per ogni runlevel bisognava modificare il file presente in `/etc/inittab`.
Questo file modificabile con NANO presentava la seguente sintassi per indicare i processi o i demoni che dovevano avviarsi in un specifico runlev : 

`id:runlevel:action:process`
*esempi :
- x:5:/etc/X11/prefdm -nodaemon
- ca:(*vuoto =  in ogni runlevel*):crtlaltdel:/sbin/shutdown/ -t3 -r now

Sugli **UbuntuServer** `12.04` e successive questo file è ora presente in `/etc/init/rc-sysinit.conf`.

Tramite il comando : 

```bash
ls -lah /etc/init.d
```

Il sistema ci mostra un elenco di tutti i demoni presenti in `init.d`. Questi script sono utilizzati dal sistema per gestire i servizi durante il processo di avvio e spegnimento del sistema.

## Visualizzare i demoni e la loro struttura

Come detto in precedenza ogni Runlevel, tramite il sistema di init, fa partire specifici demoni, necessari per quel runlevel. I demoni che devono essere lanciati ad ogni runlevel sono presenti nella cartella `/etc`.

Per visualizzare i demoni che verranno lanciati per esempio a runlevel 6, basta digitare il seguente comando : 

```bash
ls -lah /etc/rc6.d
```

`-l` : vediamo una descrizione più accurata dei file.
`-a` : per vedere i file nascosti.
`-h` : sta per *human readeble*, mostra in KiloByte in MegaByte.

Infine passiamo `rcX`, dove `x` è il numero del runlevel di cui vogliamo vedere i demoni.

Ogni demone avrà una sintassi del genere : `S01apache2 -> ../init.d/apache2`

Se ci troviamo in una delle cartelle `rc` tutti i demoni saranno collegamenti simbolici al file `init.d`.

Ogni demone può iniziare con due lettere `S` (start) o `K` (kill).
Il numero affianco alla lettere rappresenta l'ordine nel quale devono essere avviati o uccisi i demoni.

un file di configurazione controlla sia l’avvio che il termine di quel processo
invece di service ssh stop
possiamo scrivere direttamente “stop ssh” piuttosto che “status ssh”
non abbiamo più bisogno dei link simbolici perché controlliamo l'avvio
per controllare quali servizi sono in esecuzione: initctl list
status ssh per controllare lo stato di esecuzione di un servizio
## Gestione dei demoni

Un tool molto semplice ed efficace è `sysv-rc-conf` disponibile sono per le macchine che utilizzano ancora Sys V. 

Per i sistemi moderni che utilizzano `system d` , si possono digitare i seguenti comandi:  

 *elencare tutti i servizi*
```bash
systemctl list-unit-files --type=service
```

*elencare tutti i servizi collegati ad un target*
```bash
systemctl list-dependencies reboot.target
```

*abilitare un servizio*
```bash
sudo systemctl enable nome_servizio
```

*disabilitare un servizio*
```bash
sudo systemctl disable nome_servzio
```

*avviare un servizio*
```bash
sudo systemctl start nome_servzio
```

*fermare un servizio*
```bash
sudo systemctl stop nome_servzio
```
## References

- [[Unita,stato e preset]]
- [[Sviluppo di un Demone (tomcat)]]
- [[Runlevel e la diagnostica al boot]]