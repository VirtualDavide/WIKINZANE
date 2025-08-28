2025-04-20 20:53

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]]

# Progettare il partizionamento dei dischi

Quando si installa un sistema Linux, uno degli aspetti più trascurati ma fondamentali riguarda la gestione delle partizioni. È facile cadere nell'errore **di lasciare tutto su una singola partizione**, magari perché si va di fretta o perché non si ha ancora ben chiaro come organizzare lo spazio su disco. Tuttavia, a lungo termine, questa scelta può rivelarsi problematica, specialmente quando ci si trova con la root piena, oppure con directory come `/var` o `/home` che crescono molto più del previsto. In questi casi, è utile saper analizzare la situazione attuale, comprendere come sono montate le partizioni, e – se necessario – intervenire anche a posteriori.

Per cominciare, uno degli strumenti più immediati da usare è il comando `df`. Scrivendo `df -h`, **otteniamo un quadro generale dell’utilizzo del disco in formato leggibile dall'essere umano**, quindi in MB o GB anziché in byte. Un'alternativa è `df -H`, che invece usa multipli da 1000 (*1 kB = 1000 B*) anziché i classici 1024, una differenza che può sembrare sottile ma che ha un impatto, soprattutto in contesti dove le cifre devono “sembrare” più convenienti – come ad esempio nelle offerte degli operatori telefonici. A queste opzioni possiamo aggiungere `-T`, quindi `df -hT`, per avere anche il tipo di file system associato a ogni partizione.

Da qui è possibile osservare come siano distribuite le partizioni: potremmo trovarne una con tipo `xfs` montata su `/`, che rappresenta la root, magari con 8 GB totali, 5 utilizzati e 3 disponibili. Altre voci interessanti sono i vari `tmpfs`, file system temporanei in RAM, montati su percorsi come `/dev` o `/dev/shm`. Questi ultimi non occupano spazio su disco, ma sono fondamentali per il funzionamento del sistema.

Una situazione tipica è vedere una partizione `/dev/sda1` di circa 497 MB, montata su `/boot`. Questo è uno degli esempi di suddivisione corretta, dove si tiene separata la partizione di avvio dal resto del sistema. Ma cosa succede se ci accorgiamo troppo tardi che la nostra `/home` sta riempiendo tutta la root, o che `/var` – *magari su un server – sta crescendo rapidamente per via dei log o dei database?*

A quel punto, bisogna intervenire. E sì, si può fare anche dopo l’installazione. Si può, ad esempio, creare una nuova partizione o collegare un nuovo disco, formattarlo con un file system adatto (ad esempio `xfs` o `ext4`) usando strumenti come `mkfs.xfs /dev/sdb1`, e poi montarlo temporaneamente con `mount /dev/sdb1 /mnt`. A quel punto, si possono spostare i dati della directory interessata, diciamo `/var`, usando `rsync -avx /var/ /mnt`, rinominare la vecchia cartella (ad esempio con `mv /var /var.old`) e poi montare il nuovo disco su `/var` con `mount /dev/sdb1 /var`. Infine, si aggiorna `/etc/fstab` per rendere il cambiamento permanente al riavvio.

Tutto questo richiede attenzione e ordine. È importante fare un uso saggio delle partizioni già all'installazione, ma è altrettanto importante saper intervenire a sistema avviato, con strumenti come `df`, `mount`, `rsync`, e una buona conoscenza della gerarchia del file system secondo lo standard FHS, che definisce dove vanno collocati i file e perché ha senso separare determinate directory.

Organizzare bene le partizioni non è solo una questione tecnica: è un modo per garantire stabilità, sicurezza e scalabilità al proprio sistema Linux, sia che si tratti di un server, di un desktop, o di una macchina virtuale.
## References

- [[Partizionamento e montaggio d'emergenza (var)]]