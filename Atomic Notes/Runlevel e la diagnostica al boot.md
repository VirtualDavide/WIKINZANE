2025-01-01 21:00

Tags : [[Architettura del sistema]] / [[101.2]]

# Runlevel e la diagnostica al boot

Dal bootloader posso specificare quale runlevel (*targhet*) eseguire. Per farlo non basta far altro che : 

(*in ambiante Linux con grub*)
1. Selezionare il sistema operativo desiderato.
2. Cliccare `e` per andare in **edit mode**.
3. Tramite le freccette andare alla fine della stringa di boot del kernel 
	1. *esempio di stringa : * `linux /vmlinuz-5.10.0-8-amd64 root=/dev/sda1 ro quiet initrd /initrd.img-5.10.0-8-amd64
4. Digitare il numero del runlevel da cui si vuole avviare il sistema (*0,1,2,3,5*).
5. Digitare `Ctrl + x` o `F10` per eseguire.

possiamo vedere i parametri con cui abbiamo lanciato il kernel con il comando : 

```bash
cat /proc/cmdline
```

La modifica al bootloader non rimane in memoria e viene cancellata al prossimo avvio del sistema.

Possiamo vedere quale è il runlevel in esecuzione con il comando : 

```bash
runlevel
```

Vedere qual'è il run level di default con il comando : 

```bash
systemctl get-default
```

o modificare il runlevel di default con il comando : 

```
systemctl set-default nomedeltarget
```

Possiamo vedere i vari runlevel del sistema tramite il comando : 

```bash
ls -l /lib/systemd/sistem runlevel*.target
```
`
Se dopo la fase di caricamento del kernel, dovessero risultare dei problemi con gli [[Init del SO]], possiamo provare a ripristinarlo avviando un programma differente all'avvio. Ad esempio, specificando `init=/bin/sh` (*sempre in fase di edit di grub*) avvia il sistema in una shell sh con privilegi di root, da quale possiamo essere in grado di riparare il sistema.

Per cambiare il runlevel in esecuzione a sistema avviato, tramite il comando : 

```bash
sudo telinit numeroDelRunlevel
```

Gli eventi generati dal kernel durante la fase di boot sono registrati all'interno del seguente file :

```bash
sudo cat /var/log/boot.log
```

Una volta eseguito il boot, il SO non scrive più su questo file. (*in alcune versioni Linux, questo file può chiamarsi  `boot.msg`)

Una volta che il sistema è avviato possiamo leggere i comandi tramite : 

```bash
sudo dmesg
```


## References

- [[Init del SO]]
- [[Runlevel]]
- [[Leggere i log con Journalctl]]
- [[Runlevel e Demoni]]