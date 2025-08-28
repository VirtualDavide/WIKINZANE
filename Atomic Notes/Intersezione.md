2025-03-19 17:51

Tags : [[SQL]]

# Intersezione

L'**intersezione** delle relazione R e S, denota come R∩S, è l'insieme delle righe che sono presenti in R e contemporaneamente in S.

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

L'intersezione delle tabelle è la seguente : 

**Tabella R∩S**

| d   | a   | f   |
| --- | --- | --- |

Anche l'intersezione richiede che le tabelle siano compatibili. Dall'esempio si vede chiaramente come il risultato di questa operazione sia la sola riga (*d,a,f*) in quanto unica a essere presente sia nella prima sia nella seconda tabella.
## References

- [[Teoria degli Insiemi]]