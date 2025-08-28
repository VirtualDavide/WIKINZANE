2025-03-19 17:58

Tags : [[SQL]]

# Differenza

La **differenza** delle relazioni R e S, denota come R-S, e l'insieme delle righe che sono presenti in R ma che non sono presenti in S. 

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

La differenza delle tabelle è la seguente : 

**Tabella R-S**

|  a  |  b  |  c  |
| :-: | :-: | :-: |
|  c  |  b  |  d  |

Come si può vedere dall'esempio, abbiamo eliminato la riga (*d,a,f*) poichè presente anche nella tabella S. Ovviamente l'operazione cambia in base alla tabella su cui applichiamo la differenza. Infatti se avessimo fatto la differenza **S-R la tabella** risultate sarebbe stata : 

**Tabella S-R**

| b   | g   | a   |
| --- | --- | --- |
Un esempio potrebbe essere : 
Abbiamo una tabella che contiene i contatti di persone che abbiamo prelevato tramite campagne pubblicitarie, mentre in un altra tabella potremmo avere i contatti dei nostri clienti. Facendo la differenza tra la tabella *contatti compagna* e *clienti* potremmo sapere quando persone non sono ancora nostri clienti o quante lo sono diventate.

## References

- [[Teoria degli Insiemi]]
