2025-03-23 20:24

Tags : [[Docker]]

# Registry e Repository

Importanza di comprendere i termini "registry" e "repository" nel contesto di Docker.

### Cos'è un Registry?
- Definizione: Un registry è un sistema che contiene un elenco di repository.
- Funzione: Agisce come un "elenco telefonico" per le immagini Docker, facilitando la ricerca e il download.

### Cos'è un Repository?
- Definizione: Un repository è un magazzino che contiene tutte le versioni di un certo software.
- Esempio: Repository di Apache su Docker Hub, dove sono elencate tutte le versioni disponibili.

### Interazione tra Registry e Repository
- Processo di ricerca: Quando si cerca un software (es. Apache) su Docker Hub, si accede direttamente alla pagina del repository.

### Diversità dei Registry
- Esistenza di più registry: Oltre a Docker Hub, ci sono altri registry come CCR, GitHub Container Registry, Red Hat, ecc.
- Ogni registry può avere un elenco diverso di repository.

### Compatibilità delle Immagini
- **Standard Open Container Image**: Tutte le immagini scaricate da diversi registry aderiscono a questo standard, garantendo compatibilità con Docker, Podman e altri container engine.

## References

- [[Docker vs Podman]]