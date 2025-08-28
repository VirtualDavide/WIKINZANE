2025-07-26 14:40

Tags : [[DailyLinux]] [[RAID]]

# RAID - cos'è, a cosa serve e come funziona

**RAID**(*Redundant Array of Independent Disks*), ci riferiamo a una tecnologia utilizzata per combinare più dischi rigidi in un unico sistema (*i dati sono distribuiti su più dischi*). *Perchè fare questo ?*
In sostanza RAID nasce con l'obiettivo di migliorare le prestazioni di archiviazione e l'affidabilità dei dati in modo efficiente.

Questa tecnologia è particolarmente usata in ambito professionale, come nei server o nei sistemi di archiviazione di grandi quantità di dati, ma è utile anche per utenti domestici che vogliono maggiore sicurezza.

## I livelli di RAID
Esistono diversi **livelli di RAID**, ciascuno con caratteristiche diverse, in modo diverso le prestazioni, la capacità e la sicurezza dei dati.

### RAID  0 : Lo striping
Il livello più semplice è il RAID 0. Qui i dati vengono divisi in blocchi e scritti contemporaneamente su tutti i dischi. Questo processo si chiama *striping*. Il risultato è un aumento notevole della velocità, perché più dischi lavorano insieme. Tuttavia, non c'è alcuna protezione. Se anche solo un disco si guasta, si perdono tutti i dati. *È come tagliare un testo in tanti pezzi e spargerlo su più quaderni, se uno si perde, il testo è incompleto*. 

- **Spazio disponibile  :** numero dischi × dimensione singolo disco
- **Dischi minimi :** 2
- **Guasti tollerabili** : 0 (*nessuna tolleranza*)

### RAID 1 : il mirroring
Nel RAID 1, invece, i dati vengono copiati integralmente su due o più dischi. Questo sistema si chiama *mirroring*. Se un disco di rompe, c'è una copia esatto pronta all'uso. La sicurezza è molto alta, ma lo spazio utile è ridotto alla capacità del singolo disco, perchè si fanno duplicati.

- **Spazio disponibile  :** dimensione di un disco (i dati sono duplicati)
- **Dischi minimi :** 2
- **Guasti tollerabili** : numero dischi - 1

### RAID 5 : striping con parità
Il **RAID 5** è un compromesso intelligente. I dati sono suddivisi e distribuiti su più dischi, come del RAID 0, ma viene aggiunta una speciale informazione chiamata *parità*, distribuita su tutti i dischi. Questa parità permette di ricostruire i dati nel caso di guasto di un disco, offrendo una buona sicurezza senza perdere troppo spazio. Però la scrittura dei dati è un po' più lenta, perché il sistema deve calcolare la parità

- **Spazio disponibile  :** (numero dischi - 1) × dimensione singolo disco
- **Dischi minimi :** 3
- **Guasti tollerabili** : 1

### RAID 6 : doppia parità
Il **RAID 6** estende il RAID 5, aggiungendo una seconda parità. Questo permetti di tollerare la perdita di due dischi contemporaneamente, aumentando la sicurezza ma riducendo ulteriormente lo spazio disponibile e rallentando le scritture.

- **Spazio disponibile  :** (numero dischi - 2) × dimensione singolo disco
- **Dischi minimi :** 4
- **Guasti tollerabili** : 2

### RAID 10 : combinazione di mirroring e striping 
Infine, il **RAID 10** (*detto anche 1+0*) combina RAID 1 e RAID 0. Si crea prima un mirroring dei dischi a coppie, e poi questi insiemi vengono messi in striping. Così si ottiene un sistema molto veloce e molto sicuro, ideale per chi vuole il meglio da entrambi i mondi. Il contro è che serve almeno 4 dischi e lo spazio disponibile è la metà di quello totale.

- **Spazio disponibile  :** (numero dischi / 2) × dimensione singolo disco
- **Dischi minimi :** 4
-  **Guasti tollerabili** : 1 per coppia.
### RAID 50 : combinazione di RAID 5 e RAID 0

Il **RAID 50** combina i vantaggi del RAID 5 e del RAID 0. Si creano prima diversi array RAID 5, e poi questi array vengono messi in striping. Questo sistema offre una buona velocità e una buona tolleranza ai guasti, permettendo di recuperare da un guasto in ciascun sotto-array RAID 5. Tuttavia, la configurazione è complessa e richiede molti dischi.

- **Spazio disponibile :** (numero dischi - numero sotto-array × 1) × dimensione singolo disco
- **Dischi minimi :** 6 (2 sotto-array RAID 5 con 3 dischi ciascuno)
- **Guasti tollerabili** : 1 per sotto-array RAID 5

### RAID 60 : combinazione di RAID 6 e RAID 0

Il **RAID 60** combina i vantaggi del RAID 6 e del RAID 0. Si creano prima diversi array RAID 6, e poi questi array vengono messi in striping. Questo sistema offre una elevata tolleranza ai guasti, permettendo di recuperare da due guasti in ciascun sotto-array RAID 6. Tuttavia, la configurazione è complessa e richiede molti dischi, inoltre le prestazioni di scrittura possono essere ridotte a causa del calcolo della doppia parità.

- **Spazio disponibile :** (numero dischi - numero sotto-array × 2) × dimensione singolo disco
- **Dischi minimi :** 8 (2 sotto-array RAID 6 con 4 dischi ciascuno)
- **Guasti tollerabili** : 2 per sotto-array RAID 6

Questi livelli RAID avanzati sono ideali per ambienti dove sia la velocità che la tolleranza ai guasti sono critiche, ma richiedono una pianificazione attenta e risorse significative.

### Tabella riassuntiva

| Livello RAID | Min. dischi richiesti | Guasti tollerabili (massimo) | Formula spazio disponibile | Efficienza (%)        |
| ------------ | --------------------- | ---------------------------- | -------------------------- | --------------------- |
| **RAID 0**   | 2                     | **0** (nessuna tolleranza)   | `n × s`                    | 100%                  |
| **RAID 1**   | 2                     | **n − 1**                    | `s`                        | `100% / n`            |
| **RAID 5**   | 3                     | **1 disco**                  | `(n − 1) × s`              | `((n − 1) / n) × 100` |
| **RAID 6**   | 4                     | **2 dischi**                 | `(n − 2) × s`              | `((n − 2) / n) × 100` |
| **RAID 10**  | 4 (pari)              | **1 per coppia**             | `(n / 2) × s`              | 50%                   |
| **RAID 50**  | 6 (es. 2 gruppi da 3) | **1 per gruppo RAID 5**      | `((n / g) × (g − 1)) × s`  | Dipende dai gruppi    |
| **RAID 60**  | 8 (es. 2 gruppi da 4) | **2 per gruppo RAID 6**      | `((n / g) × (g − 2)) × s`  | Dipende dai gruppi    |

## References

- [[Configurazione livello RAID 0 con mdadm]]
- [[mdadm - RAID managing]]