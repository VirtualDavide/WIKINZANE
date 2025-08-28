2025-04-26 20:44

Tags : [[Comandi GNU e Unix]] / [[103.2]] / [[DailyLinux]]

# Dividere ed unire i file con split e cat

### Introduzione al Comando `split`
Il comando `split` è utilizzato per dividere un file in più file più piccoli. Per esempio, se si ha un file di 5000 righe, `split` può essere utilizzato per creare file più piccoli, ciascuno contenente un numero specifico di righe.

### Creazione di un File di Test
Per dimostrare l'uso di `split`, viene creato un file di testo chiamato `textfile.txt` contenente 5000 righe:
```bash
for i in {1..5000}; do echo "Riga numero $i" >> textfile.txt; done
```
Questo comando utilizza un ciclo `for` per generare il file.

### Utilizzo di `split`
- **Divisione di un File di Testo**:
  Per dividere `textfile.txt` in file di 1000 righe ciascuno:
  ```bash
  split textfile.txt
  ```
  Questo comando crea file denominati `xaa`, `xab`, `xac`, ecc., ognuno contenente 1000 righe.

- **Specificare il Numero di Righe**:
  Per dividere il file in parti di 100 righe:
  ```bash
  split -l 100 textfile.txt
  ```

- **Utilizzare un Prefisso Personalizzato**:
  Per creare file con un prefisso specifico:
  ```bash
  split -l 500 textfile.txt text_splitting_
  ```
  Questo comando genera file come `text_splitting_aa`, `text_splitting_ab`, ecc.

### Lavorare con File Binari
Il comando `split` può essere utilizzato anche con file binari, come video o archivi. Ad esempio, per dividere un file video in parti di 5 MB:
```bash
split -b 5M video.mp4
```
Questo comando crea file di dimensioni specificate, come `xaa`, `xab`, ecc.

### Unire File Divisi
Per unire i file divisi, si può utilizzare il comando `cat`. Ad esempio, per unire i file video:
```bash
cat xaa xab xac > video_unito.mp4
```
Questo comando concatena i file in un nuovo file chiamato `video_unito.mp4`.

### Verifica del File Unito
Dopo aver unito i file, è possibile verificare che il file risultante sia riconosciuto come un file video:
```bash
file video_unito.mp4
```
Questo comando mostra il tipo di file, confermando che è un file MP4.

## References

- [[Le meraviglie di Cut]]