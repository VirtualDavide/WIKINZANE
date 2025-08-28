2025-03-19 18:16

Tags : [[SQL]]

# Prodotto Cartesiano

Il **prodotto cartesiano** (*o semplicemente prodotto*), di due tabelle R e S, denoto come RxS, è l'insieme delle righe concatenando ogni riga di R con ogni riga di S.

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

Il prodotto delle tabelle è il seguente : 

**Tabella RxS**

|  a  |  b  |  c  |  b  |  g  |  a  |
| :-: | :-: | :-: | :-: | :-: | :-: |
|  a  |  b  |  c  |  d  |  a  |  f  |
|  d  |  a  |  f  |  b  |  g  |  a  |
|  d  |  a  |  f  |  d  |  a  |  d  |
|  c  |  b  |  d  |  b  |  g  |  a  |
|  c  |  b  |  d  |  d  |  a  |  f  |

## References

- [[Teoria degli Insiemi]]
- [[Join(equi)]]