2025-01-05 19:30

Tags : [[Sistemi Distribuiti]]

# Architetture Distribuite

Le quattro principali architetture distribuite sono:

1. **SISD (Single Instruction stream Single Data stream)**:
    - In questa architettura, un singolo processore esegue una singola sequenza di istruzioni su un singolo flusso di dati. È il modello tradizionale di elaborazione, tipico dei computer a singolo processore. 
2. **SIMD (Single Instruction stream Multiple Data streams)**:
    - In un'architettura SIMD, un singolo processore esegue la stessa istruzione su più flussi di dati contemporaneamente. Questo è utile per operazioni che possono essere parallelizzate, come il processamento di immagini o il calcolo di vettori. 
3. **MISD (Multiple Instruction streams Single Data stream)**:
    - In un'architettura MISD, più processori eseguono istruzioni diverse su un singolo flusso di dati.
4. **MIMD (Multiple Instruction streams Multiple Data streams)**:
    - In un'architettura MIMD, più processori eseguono istruzioni diverse su flussi di dati diversi. Essi si dividono in : 
	    - **multiprocessori** : I sistemi a multiprocessore sono architecture a **memoria condivisa**, la memoria è in comune e quindi esiste un unico spazio di indirizzamento per tutti i processi.
	    - **multicomputer** : Ogni computer possiede una memoria privata, non indirizzabile da altri processi remoti e la comunicazioni con altri avviene solo tramite **scambio di messaggi**.
## References

- [[I Sistemi Distribuiti]]
- [[Classificazione Sistemi Distribuiti]]