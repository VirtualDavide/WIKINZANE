2025-04-10 16:31

Tags : [[DailyLinux]]

# Vim - comandi utili

Vim è un editor di testo molto potente e versatile. Ha diverse modalità, ma le più comuni sono la modalità Normale, la modalità Inserimento e la modalità Visuale.

### Modalità Normale
In questa modalità, puoi navigare e modificare il testo. Puoi entrare in modalità Normale premendo `Esc`.

#### Navigazione
- `h` - Muovi a sinistra
- `j` - Muovi in basso
- `k` - Muovi in alto
- `l` - Muovi a destra
- `gg` - Vai all'inizio del file
- `G` - Vai alla fine del file
- `0` - Vai all'inizio della riga
- `$` - Vai alla fine della riga
- `w` - Vai alla prossima parola
- `b` - Torna indietro alla parola precedente

#### Modifica
- `i` - Entra in modalità Inserimento prima del cursore
- `a` - Entra in modalità Inserimento dopo il cursore
- `o` - Aggiungi una nuova riga sotto e entra in modalità Inserimento
- `O` - Aggiungi una nuova riga sopra e entra in modalità Inserimento
- `x` - Elimina il carattere sotto il cursore
- `dd` - Elimina la riga corrente
- `yy` - Copia la riga corrente
- `p` - Incolla il contenuto copiato dopo il cursore
- `P` - Incolla il contenuto copiato prima del cursore
- `u` - Annulla l'ultima azione
- `Ctrl + r` - Ripristina l'ultima azione annullata

#### Copiare e Modificare Parti Specifiche di Testo
- **Copiare una parte specifica**:
  1. Posiziona il cursore all'inizio della parte che desideri copiare.
  2. Premi `v` per entrare in modalità Visuale.
  3. Usa i tasti di navigazione per selezionare il testo desiderato.
  4. Premi `y` per copiare il testo selezionato.

- **Modificare una parte specifica**:
  - `ciw` - Cambia (cambia e copia) la parola sotto il cursore.
  - `ci"` - Cambia (cambia e copia) il testo all'interno delle virgolette.
  - `ci(` - Cambia (cambia e copia) il testo all'interno delle parentesi.
  - `c$` - Cambia (cambia e copia) il testo dalla posizione corrente fino alla fine della riga.

#### Ricerca
- `/testo` - Cerca "testo" nel file
- `n` - Vai alla prossima occorrenza della ricerca
- `N` - Vai all'occorrenza precedente della ricerca

#### Salvataggio e Uscita
- `:w` - Salva il file
- `:q` - Esci da Vim
- `:wq` - Salva e esci
- `:q!` - Esci senza salvare

### Modalità Inserimento
In questa modalità, puoi inserire testo. Puoi entrare in modalità Inserimento premendo `i`, `a`, o `o`. Per tornare alla modalità Normale, premi `Esc`.

### Modalità Visuale
In questa modalità, puoi selezionare il testo. Puoi entrare in modalità Visuale premendo `v` (per selezione carattere) o `V` (per selezione riga). Per tornare alla modalità Normale, premi `Esc`.

### Comandi Aggiuntivi
- `:set nu` - Mostra i numeri di riga
- `:set nonu` - Nasconde i numeri di riga
- `:help` - Mostra la guida di Vim

---

Questa nota ora include informazioni su come copiare e modificare parti specifiche di testo, utilizzando il tasto `c` e altre combinazioni. Se hai bisogno di ulteriori dettagli o chiarimenti, non esitare a chiedere!
## References

- [[Vim]]