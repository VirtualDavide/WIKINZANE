2025-04-21 08:50

Tags : [[Installazione di Linux e Package Management]] / [[102.2]]

# Grub2

GRUB 2 **non è** semplicemente una nuova versione di GRUB 1. È proprio un **cambio di paradigma**. Se con GRUB 1 eri abituato a editare direttamente `/boot/grub/menu.lst` o `grub.conf`, con GRUB 2 ti trovi davanti un sistema **molto più dinamico**, costruito su script, moduli e automazione.

GRUB 1 era tutto sommato semplice: scrivevi tu a mano ogni voce di menu, ogni riga per il kernel. Non c’erano regole imposte da rispettare, tutto era piuttosto “manuale”. Il vantaggio? Controllo diretto e immediato. Lo svantaggio? Ogni cambiamento doveva essere scritto a mano, e bastava un errore per bloccare il boot del sistema.

GRUB 2 invece è progettato per essere **automatizzato**. È pensato per funzionare su sistemi complessi, supportare UEFI, GPT, configurazioni multiple e aggiornamenti frequenti. Per questo non lavora su un file statico: genera dinamicamente il file `/boot/grub2/grub.cfg` (o `/boot/grub/grub.cfg` a seconda della distro), **partendo da una serie di file sorgente**.

Ecco il cuore del discorso: con GRUB 2 **non modifichi mai direttamente `grub.cfg`**, perché verrebbe sovrascritto. Agisci sulle sue **fonti**, poi usi il comando `grub2-mkconfig` per rigenerare tutto.

### 🛠️ **Come si cambiano davvero le configurazioni su GRUB 2**


#### 1. **Timeout di GRUB (tempo prima del boot automatico)**

Se vuoi cambiare i secondi che GRUB aspetta prima di avviare automaticamente il kernel predefinito:

- Apri il file:

```bash
 sudo vi /etc/default/grub
```

Cerca la riga:

```bash
GRUB_TIMEOUT=5
```
## References

- [[Grub Legacy]]
- [[Modifica Grub2 - Ubuntu]]