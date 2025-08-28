2025-04-21 09:37

Tags : [[Installazione di Linux e Package Management]] / [[102.3]]

# Librerie condivise (shared libraries)

### Gestione delle Librerie Condivise in Linux

In Linux, la gestione delle librerie condivise è un aspetto cruciale per il funzionamento efficiente dei programmi. Le librerie condivise, simili alle DLL (*Dynamic Link Libraries*) in Windows, consentono ai programmi di utilizzare codice riutilizzabile, riducendo la duplicazione e migliorando l'efficienza. Questo approccio permette di mantenere i programmi leggeri e modulari.

I programmi possono essere suddivisi in due categorie principali in base all'uso delle librerie:

1. **Eseguibili Dinamici**: Questi programmi fanno riferimento a librerie esterne per funzionare. Utilizzano codice condiviso, il che significa che non contengono tutte le librerie necessarie al loro interno. 
    
2. **Eseguibili Statici**: Questi programmi includono tutte le librerie necessarie al loro interno, rendendoli indipendenti dalla presenza di librerie esterne. 

#### Esempio di Librerie Condivise

Prendiamo come esempio il comando `ls`, che è utilizzato per elencare i file in una directory. Questo comando non contiene tutto il codice necessario per gestire l'output, ma si affida a librerie esterne. Quando eseguiamo `ls`, il sistema operativo carica le librerie necessarie, permettendo al comando di funzionare correttamente senza dover includere ogni singola funzione al suo interno.

### Gestione delle Librerie tramite `/etc/ld.so.conf`
Per analizzare quali librerie un eseguibile utilizza, possiamo utilizzare il comando `ldd`. Ad esempio, eseguendo `ldd /bin/ls`, possiamo vedere un elenco delle librerie condivise di cui `ls` ha bisogno per funzionare. 
Se eseguiamo lo stesso comando sulla versione statica, il risultato indicherà che non ci sono librerie esterne, poiché tutte le dipendenze sono già incorporate nell'eseguibile.

Inoltre, il comando `ldconfig` è fondamentale per aggiornare la cache delle librerie condivise. Quando installiamo nuove librerie o modifichiamo i percorsi delle librerie esistenti, dobbiamo eseguire `ldconfig` per garantire che il sistema riconosca le nuove librerie. Questo comando legge i file di configurazione in `vi /etc/ld.so.conf` e aggiorna la cache, permettendo ai programmi di trovare le librerie necessarie.

### Gestione delle Librerie tramite `LD_LIBRARY_PATH`
Le librerie condivise sono generalmente collocate in directory standard come `/lib`, `/lib64`, e `/usr/lib`. Tuttavia, è possibile aggiungere percorsi personalizzati per le librerie. Ad esempio, se stiamo sviluppando una nuova libreria e vogliamo testarla senza modificare il sistema, possiamo creare una directory chiamata `/lib2` e copiare la nostra libreria lì. Utilizzando la variabile d'ambiente `LD_LIBRARY_PATH`, possiamo specificare a Linux di cercare anche in questa nuova directory.

Ecco un esempio pratico: supponiamo di avere una libreria chiamata `libmialibreria.so` in `/lib2`. Prima di eseguire un programma che dipende da questa libreria, possiamo impostare la variabile d'ambiente:

```bash
export LD_LIBRARY_PATH=/lib2:$LD_LIBRARY_PATH
```

Dopo aver esportato questa variabile, quando eseguiamo il programma, il sistema cercherà prima in `/lib2` per trovare `libmialibreria.so`, permettendoci di testare le modifiche senza influenzare le librerie di sistema.
## References

- 