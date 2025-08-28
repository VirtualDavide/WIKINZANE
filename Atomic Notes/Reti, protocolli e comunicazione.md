2025-01-05 20:13

Tags : [[Applicazioni di Rete]]

# Reti, protocolli e comunicazione

Il principale scopo delle reti è quello di condividere dati tramite le applicazioni.

Un applicazione di rete è costituita da un insieme di programmi che vengono eseguiti contemporaneamente si più macchine, mediante risorse comuni.
La comunicazione avviene tramite **protocolli di comunicazione**, essi infatti stabiliscono un insieme di regole tra gli interlocutori (***host***) affinché possano comprendersi. La tecnologia usata per comunicare è quella dello **scambio di messaggi**. 

I principali protocolli di comunicazione principali sono due : 

1. **UDP** : protocollo senza connessione, orientato alla velocità, piuttosto che all'affidabilità.
2. **TCP** : protocollo affidabile, segnala gli errori e controlla l'integrità dell'informazione, questo grava sulle prestazioni.

I protocolli applicazione quindi, in base alle loro esigenze si appoggiano su uno di questi due, nello specifico : 

| APPLICAZIONE | COMUNICAZIONE |
| ------------ | ------------- |
| SNMP         | UDP           |
| POP3         | TCP           |
| DNS          | UDP           |
| HTTP         | TCP           |
| SMTP         | TCP           |
| FTP          | TCP           |

## References

- [[Architetture Distribuite]]
- [[Socket]]