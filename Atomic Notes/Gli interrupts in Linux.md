2024-12-30 21:06

Tags : [[Architettura del sistema]] / [[101.1]]

# Gli interrupts in Linux

Le periferiche, come le tastiere, le porte seriali e parallele, **comunicano al processore tramite gli interrupts**.

Tramite gli interrupts le periferiche **segnalano che un evento specifico è avvenuto e richiede attenzione**. Questo segnale quindi interrompe temporaneamente l'esecuzione del programma corrente, permettendo al processore di gestire l'evento.

In Linux possiamo vedere gli interrupts in uso e quale e quante volte il processore è stato interrotto da uno specifico interrupts con il comando : 

```shell
cat /proc/interrupts
```

Ogni volta con il comando andiamo a vedere il numero che identifica l'interrupts, quante volta ha interrotto una determinata CPU, la tipologia di interruzione e il nome completo della periferica che ha segnalato le interruzioni, (*i8042 è la tastiera*).

Il file non è **persistente** e viene rigenerato all'avvio del sistema operativo.
## References

- [[Ioports]]