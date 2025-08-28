2025-03-21 09:33

Tags : [[SQL]]

# Join(natural)

Una variante dell'operazione equi join è la **natural join**. SI tratta di una equi join, per la quale vengono eliminate le tabelle ridondanti.

*esempio :*

| R.A | R.B | R.C | S.A | S.B |
| :-: | :-: | :-: | :-: | :-: |
|  1  |  2  |  3  |  1  |  5  |
|  7  |  8  |  9  |  7  |  2  |

Partendo dalla tabella su cui è stata già eseguita un'equi join, andiamo con la natural join a rimuovere le colonne ridondanti, ottenendo il seguente risultato : 

| R.A | R.B | R.C | S.B |
| :-: | :-: | :-: | :-: |
|  1  |  2  |  3  |  5  |
|  7  |  8  |  9  |  2  |
## References

- [[Teoria degli Insiemi]]
- [[Join(equi)]]