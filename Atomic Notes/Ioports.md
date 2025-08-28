2024-12-30 21:18

Tags : [[Architettura del sistema]] / [[101.1]]

# Ioports

Ogni volta che un dispositivo invia un interrupts alla CPU, questa deve mediare il trasferimento dei dati dalla periferica e la memoria. Lo scopo delle **ioports** è **fornire ad un dispositivo un range di memoria da utilizzare.**

Ognuno di questi indirizzi di memoria **non è e non deve essere condivisibile** con gli altri dispositivi.

Con il comando : 

```shell
cat /proc/ioports
```

Possiamo vedere ogni dispositivo ed il suo relativo spazio univo di memoria corrispondente.

Il vantaggio è che stabilendo a priori gli indirizzi la CPU non deve ogni volta mediare uno spazio di memoria per la comunicazione con le periferiche.
## References

- [[Gli interrupts in Linux]]