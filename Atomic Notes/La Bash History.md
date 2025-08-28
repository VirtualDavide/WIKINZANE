2025-04-26 09:59

Tags : [[Comandi GNU e Unix]] / [[103.1]] / [[DailyLinux]]

# La Bash History

### Cos'è la History
La history è un elenco persistente dei comandi eseguiti in una sessione di terminale. Ogni volta che si esegue un comando, questo viene salvato in un file chiamato `.bash_history`, situato nella home directory dell'utente.

### Visualizzare la History
Per visualizzare la history, si utilizza il comando:
```bash
history
```
Questo comando mostra un elenco numerato dei comandi eseguiti, con i più recenti in fondo.

### Eseguire Comandi dalla History
È possibile rieseguire comandi dalla history utilizzando il numero associato a ciascun comando. Ad esempio, per rieseguire il comando numero 20:
```bash
!20
```
In alternativa, per eseguire l'ultimo comando eseguito, si può utilizzare:
```bash
!!
```

### Utilizzare Parametri dell'Ultimo Comando
Per utilizzare l'ultimo parametro dell'ultimo comando eseguito, si può usare:
```bash
!$
```
Questo è utile per evitare di riscrivere parametri lunghi.

### Navigare nella History
È possibile navigare tra i comandi precedenti utilizzando le frecce su e giù. Inoltre, si può cercare un comando specifico utilizzando:
```bash
Ctrl + R
```
Questo attiva una ricerca inversa nella history.

### Pulire la History
Per cancellare la history, si può utilizzare il comando:
```bash
history -c
```
Questo rimuove tutti i comandi dalla history.

### Comportamento dei Comandi con Spazio
Un aspetto interessante è che se un comando viene eseguito con uno spazio all'inizio, non verrà registrato nella history. Ad esempio:
```bash
 ls
```
Se eseguito come:
```bash
 ls
```
Non verrà salvato nella history.

### Disattivare l'Espansione del Punto Esclamativo
È possibile disattivare l'espansione del punto esclamativo (che consente di richiamare comandi dalla history) utilizzando:
```bash
set +o histexpand
```
Per riattivarla, si utilizza:
```bash
set -o histexpand
```

## References

- 