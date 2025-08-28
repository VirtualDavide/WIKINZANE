2025-01-22 20:21

Tags : [[DailyLinux]]

# Reimpostazione della Password di Root

Se non hai effettuato l'accesso come utente root per molto tempo e non hai salvato le informazioni di accesso da nessuna parte, è possibile che tu possa perdere l'accesso alle credenziali per il tuo sistema. 

Ma cosa fare se è necessario modificare o reimpostare la password di root?

**Nota:** per modificare la password di root, è necessario disporre della password di root corrente, dei privilegi sudo o dell'accesso fisico al sistema. Si consiglia inoltre di salvare le nuove password in un luogo sicuro a cui accedere quando necessario.

In questo articolo, tratteremo come:

1. Modifica o reimposta la password root come utente root
    
2. Modifica o reimposta la password di root come utente sudo
    
3. Modifica o reimposta la password di root utilizzando il menu GRUB
## Modifica o reimposta la password di root come utente root

Se hai la password di root attuale e desideri reimpostarla, puoi farlo utilizzando il comando `passwd`. Eseguire i seguenti passaggi per modificare o reimpostare la password dell'utente root:

Innanzitutto, accedi come utente root utilizzando il seguente comando nel Terminale:

```bash
su root
```
 
Quando ti viene chiesto di fornire la password, inserisci la password di root corrente. Successivamente, vedrai il prompt del Terminale cambiato in "#", a indicare che ora hai effettuato l'accesso come utente root.

Per modificare la password di root, digitare il seguente comando nel Terminale:

```bash
passwd
```

Ti verrà richiesto di inserire una nuova password di root. Digita la nuova password e premi il tasto **Invio**. Quindi, reinserisci la password e premi il tasto **Invio** per evitare eventuali errori di battitura.

Dopo aver inserito la password, ti verrà mostrato un messaggio che dice che la password è stata aggiornata con successo.
## Modifica o reimposta la password di root come utente Sudo

La password di root può essere modificata anche da un utente standard con privilegi sudo. È possibile modificare o reimpostare la password dell'utente root seguendo i passaggi indicati di seguito:

Digita il seguente comando come utente sudo nel Terminale per modificare la password di root.

```bash
sudo passwd root
```

Ti verrà chiesto di digitare una nuova password per l'utente root. Inserisci una nuova password e premi **Invio**. Quindi, reinserisci la password e premi il tasto **Invio** per evitare eventuali errori di battitura.

Dopo aver inserito la password, ti verrà mostrato un messaggio che dice che la password è stata aggiornata con successo.
## Modifica o reimposta la password di root utilizzando il menu GRUB

Se sei un utente root e hai dimenticato la password di root del tuo sistema, puoi reimpostarla utilizzando il menu di GRUB. GRUB è il primo programma che si avvia all'avvio del sistema. Tuttavia, tieni presente che per utilizzare il metodo descritto in questa sezione è necessario l'accesso fisico al tuo sistema.

Per reimpostare o modificare la password di root utilizzando il menu GRUB, eseguire i seguenti passaggi:

1. Riavvia il sistema e tieni premuto il tasto **Maiusc** o premi il tasto **Esc** per accedere alla modalità provvisoria (modalità di ripristino). Una volta entrato in modalità provvisoria, vedrai il menu di GRUB, come mostrato nello screenshot seguente.
2.  vai alle opzioni avanzate.
3. Quindi, per passare alla finestra di modifica, fare clic su "e" sulla tastiera.
4. Verrà visualizzata la seguente schermata: Scorri lo schermo fino a visualizzare la seguente riga: `linux /boot/vmlinuz-5.4.0-26-generic root=UUID=35\2d26aa-051e -4dbe-adb2-7fbb843f6581 ro quiet splash
5. Sostituisci '**ro**' con '**rw'** nella riga sopra e, alla fine della riga, aggiungi **'init=/bin/bash'** (`linux /boot/vmlinuz-5.4.0-26-generic root=UUID=35\  2d26aa-051e-4dbe-adb2-7fbb843f6581 rw quiet splash init=/bin/bash`).


L'aggiunta di "**rw"** e "**init=/bin/bash"** nella riga sopra indica sostanzialmente al sistema di accedere a bash con privilegi di lettura/scrittura. Tieni presente che questa configurazione verrà applicata solo per l'avvio corrente, non per gli avvii successivi.

Ora utilizza il tasto **F10** o la scorciatoia **Ctrl+X** per avviare il sistema al prompt dei comandi, come mostrato nello screenshot seguente.

Nel prompt dei comandi che appare, digita il seguente comando:
 ```bash
 passwd root
```
 
Ti verrà richiesta la password di root. Inserisci la password di root e premi il tasto **Invio** Quindi, digita nuovamente la password e premi **Invio** per evitare eventuali errori di battitura.

**Nota:** puoi modificare non solo la password di root ma anche la password di qualsiasi utente utilizzando questo processo.

Dopo aver inserito la password, verrà visualizzato un messaggio che informa che la nuova password è stata aggiornata.
## Conclusione

In questo articolo abbiamo identificato tre diversi metodi per modificare o reimpostare la password di root sul tuo sistema. Puoi optare per qualsiasi metodo, in base ai privilegi di cui disponi. Se disponi della password di root o dei privilegi sudo, puoi facilmente reimpostare la password di root utilizzando il semplice comando "passwd". Altrimenti puoi usare il menu di GRUB per cambiare la password di root, ma solo se hai accesso fisico al sistema.

Spero che questo articolo ti abbia aiutato a modificare o reimpostare la password di root del tuo sistema.
## References

- [[Boot loader Linux]]
- [[Runlevel e la diagnostica al boot]]
- [[Sudo e Su (Linux)]]