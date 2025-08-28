2025-04-26 21:44

Tags : [[Comandi GNU e Unix]] / [[103.1]]

# man e uname

#### 1. Comando `uname`

Il comando `uname` è utilizzato per stampare informazioni sul sistema operativo e sul kernel in uso. Ecco alcuni dei parametri più comuni:

- **`uname`**: Lanciato senza parametri, mostra il nome del kernel.
- **`uname -s`**: Mostra il nome del kernel (equivalente a `uname` senza parametri).
- **`uname -a`**: Mostra tutte le informazioni disponibili, inclusi:
  - Nome del kernel
  - Nome della distribuzione (es. Ubuntu)
  - Versione del kernel
  - Architettura della macchina (es. x86_64)
  - Tipo di processore
  - Piattaforma hardware
  - Sistema operativo (es. GNU/Linux)

Esempio di utilizzo:
```bash
uname -a
```

Questo comando restituirà un output simile a:
```
Linux nome-host 3.13.0-32-generic #57-Ubuntu SMP Fri Oct 10 12:34:56 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

#### 2. Comando `man`

Il comando `man` è utilizzato per visualizzare il manuale di altri comandi. È una risorsa preziosa per comprendere le opzioni e l'uso di un comando specifico.

- **`man <comando>`**: Mostra la pagina del manuale per il comando specificato.

Esempio di utilizzo:
```bash
man ls
```

Questo comando aprirà la pagina del manuale per il comando `ls`, che fornisce informazioni dettagliate su come utilizzare `ls`, comprese le opzioni disponibili.

#### Navigazione nel Manuale

All'interno della pagina del manuale, puoi navigare utilizzando le frecce su e giù. Puoi anche cercare parole chiave utilizzando `/` seguito dalla parola da cercare. Ad esempio:
```
/hidden
```
Per uscire dal manuale, puoi premere `q`.

#### Comando `whereis`

Un altro comando utile è `whereis`, che mostra la posizione dell'eseguibile di un comando e del suo file di manuale.

Esempio di utilizzo:
```bash
whereis ls
```

Questo comando restituirà la posizione dell'eseguibile `ls` e del file di manuale associato.
## References

- //