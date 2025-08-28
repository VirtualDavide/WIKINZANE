2024-12-31 11:26

Tags :[[Architettura del sistema]] / [[101.2]]

# BIOS

Il BIOS (*basic standard input/output*), è un firmware di sistema presente sulla scheda madre. Ha il compito di inizializzare e testare l'hardware del computer durante il processo di avvio (*boot*)e di caricare il sistema operativo.

Sequenza di azioni eseguite dal BIOS : 

 1. **POST**(*Power on self test*) : Tale fase esegue il controllo hardware di tutte le componenti del computer
 2. **STAGE 1 bootloader** : Dopo la fase di POST il BIOS carica lo **STAGE 1 bootloader** un programma presente all'interno del **MRB**, ovvero i primi 5121 byte del disco designato al boot del SO.
 3. **STAGE 2 bootloader** : lo STAGE 1 bootlloader è un programma molto piccolo, che ha il compito di caricare lo **STAGE 2 bootloader**.
 4. **SO**: lo **STAGE 2 bootloader** carica successivamente il sistema operativo.

In questa ultima fase, dove lo STAGE 2 bootloader carica il sistema operativo, insieme al kernel di quest'ultimo (nel caso di Linux), viene anche caricato **initrd (INITIAL RAM DISK)**.

(*può essere anche chiamato : initrd,initramfs (initial ram filesystem))*
(*in alcuni sistema come Fedora 12 viene creato utilizzando un utility chiamata dracut*)

L'initrd è un immagine di disco (moduli kernel già compilati) temporanea utilizzata nei sistemi Linux per il processo di avvio. Essa contiene un filesystem minimale e viene caricata in memoria RAM all'avvio del kernel. 

Le sue funzioni principali sono : 

1. **Driver di supporto** : L'initrd può contenere dei driver per l'hardware specifico che non è incluso nel kernel stesso.
2. **File system di appoggio** : Fornisce un file system temporaneo che il kernel può utilizzare per per accedere ai file necessari per i boot. Permette quindi al kernel di eseguire le operazioni principali prima di montare il sistema operativo. 
3. **Configurazione del sistema**: Può contenere script di avvio e configurazioni necessarie per preparare l'ambiente prima di passare al file system principale.

Un boot loader può anche caricare un altro boot loader, un esempio classico è quando abbiamo più sistemi operativi installati, infatti dopo la fase di POST, lo STAGE 1 boot loader caricherà immediatamente **grub**. **Grub** non è altro che il STAGE 2 boot loader che caricherà il sistema operativo. Nel caso in cui il sistema operativo selezionato fosse Linux, allora se ne occuperà direttamente grub, ma se invece il sistema selezionato è windows, **grub non caricherà un altro sistema operativo, bensì un altro boot loader ovvero il windows boot loader**.

(*grub non può fare il boot di windows*)

Questa tecnica si chiama **chain loading** ovvero caricamento a catena.


## References

- [[EFI-UEFI]]
- [[Boot loader Linux]]