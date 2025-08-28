2024-12-29 21:11

Tags : [[Architettura del sistema]] / [[101.1]]

# Sys fs

Sys fs è un fyle sistem virtuale presente sulle macchine Linux che fornisce l'interfaccia per l'esposizione delle informazioni sui dispositivi connessi e suo driver kernel.

È montato tipicamente nella cartella `/sys`.

`/sys` contiene diverse sottocartelle che rispecchiano i vari aspetti del sistema, le più comuni sono : 
- `/sys/block` : Contiene informazioni sui dispositivi di blocco, come i dischi rigidi e le partizioni. Ogni dispositivo di blocco ha una propria directory (ad esempio, `/sys/block/sda` per il primo disco) che contiene file con informazioni come dimensioni, stato e parametri di configurazione.
- `/sys/bus/` : Contiene le informazioni sui bus di sistema come PCI, USB e altri.
- `/sys/class/` : Contiene collegamenti simbolici a classi di dispositivi. Le classi raggruppano  dispositivi simili, come interfacce di rete, dispositivi di archiviazione ecc...Ad esempio nella cartella `/sys/class/net` possiamo trovare i collegamenti simbolici alle interfacce di rete del sistema.
- `/sys/dev` : Punto di accesso per i dispositivi e può contenere collegamenti simbolici ai dispositivi presenti nel sistema.
- `/sys/devices` : Contiene informazioni dettagliate sui dispositivi hardware collegati al sistema.
- `/sys/firmware` : Contiene informazioni di configurazione del firmware del sistema, come le configurazione del BIOS o UEFI.
- `/sys/fs` : Contiene le informazioni sui file system montati.
- `/sys/kernel` : Contiene informazioni e configurazioni relative al kernel stesso.
- `/sys/module` : Contiene informazioni su moduli del kernel attualmente caricati.
- `/sys/power` : Contiene file e cartelle relative alla gestione dell'energia.

## References

- [[Dispositivi in Linux]]