2025-01-05 16:54

Tags : [[Database]]

# Modello Relazionale

### Dati

Un modello di dai relazionale la realtà viene rappresentata nei seguenti modi : 

- **Tabella** : Ogni entità è rappresentata con una tabella.
- **Colonne** : Le colonna della tabella rappresentano gli attributi dell'entità.
- **Righe** : le singole righe vengono chiamati **record**.
- **Celle** : Le celle della tabella, atte a contenere il dato, vengono chiamate **campi**.

### Relazioni

1. **Relazione uno a uno (1:1)**:
    - In questa relazione, un record in una tabella è collegato a un solo record in un'altra tabella e viceversa.
    - Esempio: Considera una tabella "Persone" e una tabella "Passaporti". Ogni persona può avere solo un passaporto e ogni passaporto è assegnato a una sola persona.
    - **Implementazione**: Puoi avere una chiave primaria in una tabella che è anche una chiave esterna nell'altra tabella.
1. **Relazione uno a molti (1:N)**:
    - In questa relazione, un record in una tabella può essere collegato a più record in un'altra tabella, ma ogni record nella seconda tabella è collegato a un solo record nella prima tabella.
    - Esempio: Considera una tabella "Autori" e una tabella "Libri". Un autore può scrivere più libri, ma ogni libro è scritto da un solo autore.
    - **Implementazione**: La chiave primaria della tabella "Autori" diventa una chiave esterna nella tabella "Libri".
2. **Relazione molti a molti (M:N)**:
    - In questa relazione, un record in una tabella può essere collegato a più record in un'altra tabella e viceversa.
    - Esempio: Considera una tabella "Studenti" e una tabella "Corsi". Uno studente può iscriversi a più corsi e un corso può avere più studenti iscritti.
    - **Implementazione**: Per gestire questa relazione, è necessario creare una terza tabella, chiamata tabella di giunzione (o tabella di associazione), che contiene le chiavi primarie di entrambe le tabelle come chiavi esterne. Ad esempio, una tabella "Iscrizioni" potrebbe contenere le chiavi degli studenti e dei corsi.

## References

- [[Modelli di dati]] 
- [[Regole di lettura]]
- [[Regole di derivazione]]
- [[Normalizzazione]]
- [[Relazioni ed Integrità referenziale]]