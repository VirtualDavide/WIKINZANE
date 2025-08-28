2024-12-14 10:14

Tags : [[Crittografia]]
# Crittografia a chiave simmetrica

La crittografia a chiave simmetrica si basa sull'utilizzo di una sola chiave usata da mittente e destinatario per cifrare e decifrare il messaggio. 

Un esempio ci algortmo di cifratura a chiave simmetrica è il metodo XOR.

*Esempio*
Se il mittente deve inviare il messaggio in chiaro M = 11001010, con chiave K = 10100101, facendo lo XOR cifrato ottenerà il seguente messaggio cifrato C = 01101111.
Con la stessa chiave il destinatario, sarà in grado di decifrare il messaggio.

*cifratura del messaggio da parte del mittente...*

|   M   |   1   |   1   |   0   |   0   |   1   |   0   |   1   |   0   |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **K** | **1** | **0** | **1** | **0** | **0** | **1** | **0** | **1** |
| **C** | **0** | **1** | **1** | **0** | **1** | **1** | **1** | **1** |

*decifratura del messaggio dal destinatario...*

| **D** |  0  |  1  |  1  |  0  |  1  |  1  |  1  |  1  |
| :---: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **K** |  **1**  |  **0**  |  **1**  |  **0**  |  **0**  |  **1**  |  **0**  |  **1**  |
| **M** |  **1**  |  **1**  |  **0**  |  **0**  |  **1**  |  **0**  |  **1**  |  **0**  |

Nel caso dell metodo XOR, esso risulta essere ancora meno sicuro, perché il processo di cifratura e decifratura del messaggio è **identico**.
## References

- [[Sistemi crittografici]]
- [[Crittografia a chiave asimmetrica]]
- [[DES (Data Encryption Standard)]]
- [[Evoluzione del  DES (3DES, AES)]]
- [[Sistemi di identificazione digitale]]