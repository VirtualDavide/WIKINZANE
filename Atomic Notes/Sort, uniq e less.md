2025-07-19 15:28

Tags : [[Linux LPI - 101]] [[103.2]]

# Sort, uniq e less

###  **Sort**

#### Funzione
Il comando `sort` è utilizzato per ordinare le righe di un file di testo. Può gestire file di grandi dimensioni e offre diverse opzioni per personalizzare l'ordinamento.

#### Utilizzo
- **Ordinamento di base:**
  ```bash
  sort nome_file.txt
  ```
  Questo comando ordina le righe del file `nome_file.txt` in ordine alfabetico crescente.

- **Ordinamento inverso:**
  ```bash
  sort -r nome_file.txt
  ```
  L'opzione `-r` inverte l'ordine, mostrando prima le righe che normalmente verrebbero dopo.

- **Ordinamento numerico:**
  ```bash
  sort -n nome_file.txt
  ```
  L'opzione `-n` ordina le righe in base ai valori numerici. Questo è utile quando si lavora con file che contengono numeri.

- **Ordinamento per campo specifico:**
  ```bash
  sort -k 2 nome_file.txt
  ```
  Qui, `-k 2` indica che l'ordinamento deve avvenire in base al secondo campo (ad esempio, il cognome). Puoi specificare anche un intervallo di campi, come `-k 1,2` per ordinare in base ai primi due campi.

- **Ordinamento con delimitatori:**
  ```bash
  sort -t ',' -k 2 nome_file.csv
  ```
  L'opzione `-t` specifica un delimitatore (in questo caso, una virgola) per file CSV, permettendo di ordinare in base a un campo specifico.

#### Situazioni d'uso
- Ordinare elenchi di nomi, numeri o dati strutturati.
- Preparare dati per analisi successive, come la rimozione di duplicati con `uniq`.
- Creare report ordinati per una migliore leggibilità.

### **uniq**

#### Funzione
Il comando `uniq` è utilizzato per filtrare le righe duplicate in un file. Funziona meglio quando le righe duplicate sono consecutive, quindi è comune usarlo in combinazione con `sort`.

#### Utilizzo
- **Visualizzazione dei valori unici:**
  ```bash
  sort nome_file.txt | uniq
  ```
  Qui, `sort` ordina il file, e `uniq` rimuove le righe duplicate, mostrando solo le righe uniche.

- **Visualizzazione solo dei duplicati:**
  ```bash
  sort nome_file.txt | uniq -d
  ```
  L'opzione `-d` mostra solo le righe che appaiono più di una volta. Questo è utile per identificare quali elementi sono ripetuti.

- **Conteggio delle occorrenze:**
  ```bash
  sort nome_file.txt | uniq -c
  ```
  L'opzione `-c` precede ogni riga con il numero di volte che appare nel file. Questo è utile per avere un'idea della frequenza di ciascun elemento.

#### Situazioni d'uso
- Rimuovere duplicati da elenchi di contatti o dati.
- Analizzare la frequenza di parole o valori in un dataset.
- Creare report che mostrano solo valori unici o la loro frequenza.

### **less**

#### Funzione
Il comando `less` è utilizzato per visualizzare il contenuto di un file in modo interattivo. Permette di scorrere su e giù nel file senza caricarlo tutto in memoria, rendendolo ideale per file di grandi dimensioni.

#### Utilizzo
- **Visualizzazione di un file:**
  ```bash
  less nome_file.txt
  ```
  Questo comando apre il file `nome_file.txt` in `less`, permettendo di navigare attraverso il contenuto.

- **Navigazione:**
  - Usa le frecce direzionali per scorrere su e giù.
  - Premi `Space` per avanzare di una pagina.
  - Premi `b` per tornare indietro di una pagina.
  - Premi `/` seguito da un termine per cercare nel file.

- **Uscita:**
  Premi `q` per uscire da `less`.

#### Situazioni d'uso
- Visualizzare file di log o file di testo di grandi dimensioni senza caricarli completamente in memoria.
- Navigare attraverso documenti lunghi in modo interattivo.
- Cercare rapidamente informazioni specifiche all'interno di un file
## References

- 