2025-01-05 17:53

Tags : [[Database]]

# Relazioni ed Integrità referenziale

L'**integrità referenziale** è un principio nei database relazionali che garantisce che le relazioni tra le tabelle siano mantenute in modo coerente. Essa assicura che i valori delle chiavi esterne in una tabella corrispondano ai valori delle chiavi primarie in un'altra tabella. In altre parole, **non possono esistere riferimenti a record che non esistono.**
### Opzioni di Aggiornamento

Quando si aggiorna un record nella tabella padre, le seguenti opzioni possono essere applicate alle chiavi esterne nella tabella figlia:

1. **Aggiornamento a cascata (Cascade Update)**:

    - **Cosa fa**: Se un record nella tabella padre viene aggiornato (ad esempio, se cambia il valore della chiave primaria), tutti i record nella tabella figlia che fanno riferimento a quel record vengono automaticamente aggiornati per riflettere il nuovo valore. Questo mantiene la coerenza dei dati.
2. **Imposta a null (Set Null)**:
    
    - **Cosa fa**: Se un record nella tabella padre viene aggiornato, i valori della chiave esterna nei record della tabella figlia vengono impostati a null. Questo significa che i record nella tabella figlia rimangono, ma non hanno più un riferimento valido alla tabella padre.
3. **Imposta predefinito (Set Default)**:
    
    - **Cosa fa**: Se un record nella tabella padre viene aggiornato, i valori della chiave esterna nei record della tabella figlia vengono impostati a un valore predefinito specificato. Questo consente di mantenere i record nella tabella figlia, ma con un valore di chiave esterna predefinito.
### Opzioni di Eliminazione

Quando si elimina un record nella tabella padre, le seguenti opzioni possono essere applicate alle chiavi esterne nella tabella figlia:

1. **Eliminazione a cascata (Cascade Delete)**:
    
    - **Cosa fa**: Se un record nella tabella padre viene eliminato, tutti i record nella tabella figlia che fanno riferimento a quel record vengono automaticamente eliminati. Questo evita riferimenti a dati non esistenti e mantiene l'integrità referenziale.
2. **Imposta predefinito**:
    
    - **Cosa fa**: Se un record nella tabella padre viene eliminato, i valori della chiave esterna nei record della tabella figlia vengono impostati a un valore predefinito specificato. Questo consente di mantenere i record nella tabella figlia, ma con un valore di chiave esterna predefinito.
3. **Imposta a null (Set Null)**:
    
    - **Cosa fa**: Se un record nella tabella padre viene eliminato, i valori della chiave esterna nei record della tabella figlia vengono impostati a null. Questo consente di mantenere i record nella tabella figlia, ma senza un riferimento valido alla tabella padre.
## References

- [[Modello Relazionale]]