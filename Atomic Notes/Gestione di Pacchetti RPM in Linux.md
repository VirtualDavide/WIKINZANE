2025-07-24 15:27

Tags : [[Linux LPI - 101]] [[103.3]]

# Gestione di Pacchetti RPM in Linux

In Linux, i pacchetti RPM (Red Hat Package Manager) sono un formato di archiviazione standard, particolarmente utilizzato nei sistemi basati su RPM. All'interno di questi pacchetti sono contenuti degli archivi ZIP.

### Scaricamento di Pacchetti RPM

1. **Yum**: Un gestore di pacchetti che scarica e installa automaticamente i pacchetti e le loro dipendenze.
    
    `yum install httpd`
    
2. **Yumdownloader**: Un programma che scarica i pacchetti RPM senza installarli.
    
    `yumdownloader httpd`
    
3. **Yumdownloader con risoluzione delle dipendenze**: Scarica il pacchetto e tutte le sue dipendenze.
    
    `yumdownloader --resolve httpd`
    

### Estrazione di Pacchetti RPM

1. **Rpm2cpio**: Un programma che estrae il contenuto di un pacchetto RPM in un formato cpio.
    
    `rpm2cpio httpd.rpm > httpd.cpio`
    
2. **Cpio**: Un programma che estrae i file da un archivio cpio.
    
    `cpio -idmv < httpd.cpio`
    

### Visualizzazione del Contenuto di un Pacchetto RPM

1. **Rpm2cpio**: Estrae il contenuto in formato cpio.
    
    `rpm2cpio httpd.rpm`
    
2. **Cpio**: Visualizza l'elenco dei file contenuti nell'archivio cpio.
    
    `cpio -it < httpd.cpio`
    

### Creazione di Archivi ZIP

1. **Cpio**: Crea un archivio cpio da file specifici.
    
    `cpio -o test1.dat test2.dat > archive.cpio`
    
2. **Cpio**: Estrae i file da un archivio cpio.
    
    `cpio -idmv < archive.cpio`
    

### Note Importanti

- **Rpm2cpio**: Converte il contenuto di un pacchetto RPM in un formato cpio, che può essere estratto con cpio.
- **Cpio**: Un programma versatile per la gestione di archivi cpio, che può essere utilizzato per creare e estrarre archivi.
- **Parametri**: `-o` crea un archivio, `-i` estrae i file, `-d` crea le directory, `-m` mantiene i permessi, `-v` mostra i file mentre vengono estratti.

### Considerazioni Finali

- **Manuali**: I manuali (`man`) per `rpm2cpio` e `cpio` offrono molte opzioni e dettagli aggiuntivi.
- **Pipeline**: La combinazione di comandi tramite pipe (`|`) permette di concatenare operazioni in modo efficiente.
## References

- [[Yum, rpm e dnf]]