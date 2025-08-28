2024-12-29 20:40

Tags : [[Architettura del sistema]] / [[101.1]]

# Drivers Linux

I Driver permettono il corretto funzionamento di una periferica, qualsiasi dispositivi sia *cold plug* e *hot plug* hanno bisogno di Driver per funzionare.

Per visualizzare tutti i driver che sono stati caricati in memoria utilizziamo il comando `lsmod`. Tale comando mostra : 

| Module | Size (*byte*) | Used by |
| ------ | ------------- | ------- |
| ccm    | 20480         | 6       |
- *module* : il nome del modulo.
- *size*: la dimensione del modulo.
- *used by*: Il numero di dispositivi che stanno usando quel modulo.

Per rimuovere un modulo dalla memoria (RAM) possiamo utilizzare il comando : 

```shell
sudo rmmod nomedelmodulo
```

Per controllare rapidamente se il modulo non è più presente possiamo eseguire il comando : 

```shell
lsmod | greap nomedelmodulo
```

La procedura opposta è 

```shell
sudo insmod percorso/completo/del/modulo.ko
```
 
 Per ricavare tale percorso dobbiamo sapere che tutti i moduli presenti nel sistema e caricati in memoria sono presenti nella cartella `lib/modules/`. Una volta entranti troveremo tante cartella, quante sono le versione del kernel installate sul dispositivo. Ovviamente i moduli correnti, saranno nella versione del kernel in esecuzione.

Per trovare quindi il percorso del modulo che ci serve basta che digitiamo il comando :

```shell
find /lib/modules/$(uname -r)/ -iname "*nomedelmodulo.ko*"
```

- comando `uname -r` restituisce il nome della versione del kernel in esecuzione
- l'opzione `-iname "nomedelfile"` ci permette di trovare nella cartella il file specificato.
- aggiungere quale `*` può essere utili quando non sappiamo con certezza il nome preciso del modulo.

Un alternativa a `insmod` e `rmmod` è `modprobe`, infatti per rimuovere modulo dalla memoria utilizziamo il comando : 

```shell
sudo modprobe -r nomedelmodulo
```

mentre, per ricaricarlo in memoria, il comando :

```shell
sudo modprobe nomedelmodulo
```
## References

- [[Dispositivi in Linux]]