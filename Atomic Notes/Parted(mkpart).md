2025-01-22 14:53

Tags :  [[Installazione di Linux e Package Management]] / [[102.1]] [[DailyLinux]]

# Parted(mkpart)

Quando utilizzi il comando `mkpart` in `parted`, puoi specificare il tipo di partizione e, in alcuni casi, il tipo di file system. Ecco un riepilogo delle tipologie di partizione e dei file system che puoi utilizzare:

### Tipi di Partizione

1. **primary**: Partizione primaria, che può contenere un file system.
2. **logical**: Partizione logica, che è una partizione all'interno di una partizione estesa. Questo è più comune nei sistemi con una tabella delle partizioni MBR, ma non è necessario con GPT.
3. **extended**: Partizione estesa, che può contenere partizioni logiche. Anche questo è più comune con MBR.

### Tipi di File System

Quando crei una partizione, puoi specificare il tipo di file system che intendi utilizzare. Tuttavia, il tipo di file system non è un parametro obbligatorio per il comando `mkpart`. Ecco alcuni dei file system più comuni:

1. **ext4**: Uno dei file system più utilizzati su Linux, offre buone prestazioni e funzionalità.
2. **ext3**: Versione precedente di ext4, supporta il journaling.
3. **ext2**: Versione ancora più vecchia, senza journaling.
4. **xfs**: File system ad alte prestazioni, particolarmente adatto per grandi file e carichi di lavoro intensivi.
5. **btrfs**: File system moderno con funzionalità avanzate come snapshot e gestione dei volumi.
6. **FAT32**: Utilizzato principalmente per partizioni UEFI e dispositivi di archiviazione rimovibili.
7. **NTFS**: File system di Windows, può essere utilizzato per partizioni condivise tra Linux e Windows.
8. **swap**: Non è un file system tradizionale, ma viene utilizzato per la memoria di swap.
## References

- [[Parted (partizionamento Dischi)]]