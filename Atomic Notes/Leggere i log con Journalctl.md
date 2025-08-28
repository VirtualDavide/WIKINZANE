2025-01-02 11:28

Tags : [[Architettura del sistema]] / [[101.2]]

# Leggere i log con Journalctl

Jounrnalctl e un comando utilizzato nei sistemi operativi basati su Linux che utilizzano il sistema di logging chiamato `system journal`. Questo comando permette di leggere e gestire i log di sistema.

Comandi più usati con journalctl : 

```bash
journalctl
```

Ci permette di vedere tutti i log di sistema in un unica pagina, ma risulta essere scomodo.
## log di Boot

```bash
journalctl -b
```

Ci permette di vedere solo i log generati in fase di `boot` dal sistema.

```bash
journalctl -b -r
```

L'opzione `-r` corrisponde alla parola `reverse` quindi ci mostra i log dal più recente a quello più vecchio ( *di default i log sono in ordine crescente* ).

```bash
journalctl --list-boots
```

Il comando mostra un elenco delle sessioni di avvio (*boot*) registrate da journal. Ogni voce nell'elenco rappresenta un avvio del sistema e include informazioni come l'ID dell'avvio, il timestamp di inizio e fine, e lo stato dell'avvio.

```bash
journalctl -b IDboot
```

Risalendo all'ID del boot possiamo anche analizzare i log di uno specifico avvio.

## log di un determinato intervallo di tempo

```bash
journalctl --since="1 hour ago"
```

```bash
journalctl --since="2024-05-25"
```

L'opzione `--since` mostra i log da un ora o data specifica.

```bash
journalctl --since="2024-12-21" --until="2024-12-25"
```

```bash
journalctl --since="2024-12-21 10:00" --until="2024-12-25 18:00"
```

L'opzione `--until` ci permette di visione i log di un determinato intervallo di tempo.

## log utenti

```bash
journalctl _UID=997_
```

Ricavando l'ID di un utente da `/etc/passwd`, possiamo andare a visione i log generati da quell'utente in particolare.

## kernel

```bash
journalctl -k
```

Tramite journalctl possiamo vedere anche i log del kernel aggiungendo l'opzione `-k`. Il comando è equivalente a `sudo dmesg`.

## Unità e programmi

```bash
journalcl -unit=nome.service
```

L'opzione `-unit` o `-u` specifica a journal di filtrare i log di una determinata unità di sistema (*ad esempio un servizio*).

```bash
journalctl -xe | grep firefox
```

Possiamo anche controllare i log di uno specifico programma.
## References

- [[Init del SO]]
- [[Runlevel e la diagnostica al boot]]