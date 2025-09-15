Creation Date: 2025-09-15 
Creation Time: 21:54
Author: [[feb]]

## Docker vs Podman

### Origini e Popolarità
- **Docker**: Strumento pionieristico, più popolare e supportato, con una vasta gamma di guide e risorse disponibili.
- **Podman**: Sviluppato da Red Hat, preinstallato su Fedora e distribuzioni basate su Red Hat, offre vantaggi di compatibilità.

 Entrambi funzionano su Linux, Mac e Windows.
### Architettura e Gestione dei Container

Docker **utilizza un demone centrale**, mentre Podman adotta un'architettura "*daemon-less*" quindi  :  

- **Docker**: Ogni container è un processo figlio del Docker daemon; un singolo punto di fallimento.
- **Podman**: Ogni container è un processo indipendente, aumentando la resilienza e la sicurezza.

### 5. Sicurezza
- **Podman**: Esegue i container con privilegi normali dell'utente, riducendo il rischio di compromissione del sistema.
- **Docker**: Richiede privilegi di root per impostazione predefinita, aumentando il rischio in caso di attacco (*Docker può essere eseguito in modalità rootless con configurazioni aggiuntive, ma richiede limitazioni.*).
## REFERENCES
- [[Docker e Podman - concetti e terminologia]]
- [[Container e macchine virtuali]]
## TAGS
- [[Docker]]