2025-03-20 22:13

Tags : [[SQL]]

# Join

Un'operazione di **join**, detta anche **congiunzione**, combina le operazioni di **prodotto cartesiano** e di **selezione**. Infatti partendo da due tabelle, come prima cosa viene effettuato un prodotto cartesiano e, successivamente, viene operata, sulla tabella risultante, una selezione d alcune righe in base a un determinato criterio

Per questo motivo l'operazione, nel suo complesso, viene definita **equi join**.

*esempio :*

**Tabella R**

|  A  |  B  |  C  |
| :-: | :-: | :-: |
|  1  |  2  |  3  |
|  4  |  5  |  6  |
|  7  |  8  |  9  |

**Tabella S**

|  A  |  B  |
| :-: | :-: |
|  1  |  5  |
|  7  |  2  |

Il prodotto delle tabelle è il seguente : 

**Tabella RxS**

| R.A | R.B | R.C | S.A | S.B |
| :-: | :-: | :-: | :-: | :-: |
|  1  |  2  |  3  |  1  |  5  |
|  1  |  2  |  3  |  7  |  2  |
|  4  |  5  |  6  |  1  |  5  |
|  4  |  5  |  6  |  7  |  2  |
|  7  |  8  |  9  |  1  |  5  |
|  7  |  8  |  9  |  7  |  2  |

Successivamente eseguiamo una selezione che verifichi la condizione R.A = S.A. la tabella risultante sarà : 

| R.A | R.B | R.C | S.A | S.B |
| :-: | :-: | :-: | :-: | :-: |
|  1  |  2  |  3  |  1  |  5  |
|  7  |  8  |  9  |  7  |  2  |
Nell'esempio il campo A presente nelle due tabelle funge proprio da contesto chiave per legare i record della prima con la seconda tabella.
## References

- [[Teoria degli Insiemi]]
- [[Prodotto Cartesiano]]
- [[Selezione]]
- [[Join(natural)]]