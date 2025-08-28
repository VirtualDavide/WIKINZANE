2025-01-05 17:32

Tags : [[Database]]
# Normalizzazione

La **normalizzazione** è un processo composto da una serie di regole che aiutano i progettisti a organizzare in maniera corretta il proprio archivio relazionale.

Sono stati definiti vari **gradi di normalizzazione** ( *sono 9 ma consideriamo i più importanti):

1. **Prima forma normale** (1NF): Affinché una tabella sia in prima forma normale **non devono esistere colonne ripetute**, cioè non devono esistere **colonne multiple** in corrispondenza di un singolo attributo. 
	1. *Esempio* : nome1,costo1,nome2,costo2...
2. **Seconda forma normale** (2NF): La tabella deve essere almeno di prima forma normale, inoltre **tutte le dipendenze parziali devono essere eliminate** e poste in una tabella separata. Una **dipendenza parziale** si verifica quando gli attributi non dipendono in maniera piena dalla chiave primaria (*Gli attributi devono essere coerenti tra di loro*).
	1. *Esempio* : nomeCliente,costoSpedizioni,nomeFornitore,idProdotto.
3. **Terza forma normale** (3NF) : Si basa sulla seconda forma normale e richiede che non ci siano **dipendenze transitive**, ovvero che gli attributi non chiave non dipendano da altri attributi non chiave.
	1. *Esempio* : nome,cognome,città,stato (*stato dipende da città*).
## References

- [[Modelli di dati]]