2025-03-19 17:40

Tags : [[SQL]]

# Unione

L'**unione delle tabelle** R e S, denota come RUS, e l'insieme delle righe che sono presenti in R oppure in S in entrambe. 

*esempio* : 

**Tabella R**

|  A  |  B  |  C  |
| :-: | :-: | :-: |
|  a  |  b  |  c  |
|  d  |  a  |  f  |
|  c  |  b  |  d  |

**Tabella S**

|  D  |  E  |  F  |
| :-: | :-: | :-: |
|  b  |  g  |  a  |
|  d  |  a  |  f  |

L'unione delle tabelle è la seguente : 

**Tabella RUS**

| a   | b   | c   |
| :-- | :-- | :-- |
| d   | a   | f   |
| c   | b   | d   |
| b   | g   | a   |


Come possiamo vedere nell'esempio per poter realizzare l'unione tra le due tabelle è indispensabile la condizione che le tabelle coinvolte siano **compatibili** : ciò vuol dire che esse devono avere lo **stesso numero di campi** e i campi stessi devono appartenere allora **stesso dominio** (*tipologia*).

Formulando la cosa in maniera più semplice si può dire che l'unione è data dall'insieme delle righe delle due tabelle escluse eventuali duplicati.

Per interdirci se per esempio, la tabella R fosse utilizzata per conservare nome, cognome ed email, capiamo bene cosa significhi che le tabelle per unirsi devono avere lo stesso numero di campi e questi devono appartenere alla stessa tipologia.
## References

- [[Teoria degli Insiemi]]