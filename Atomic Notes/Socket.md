2025-01-05 20:36

Tags : [[Applicazioni di Rete]]

# Socket

Un host per cooperare con un altro host deve comunicare con lui. Per far ciò deve prima di tutto identificarlo. L'identificazione deve tener conto di due informazioni : 
1. **indirizzo ip**
2. **numero di porta**

L'unione di questi due dati costituisce il **Socket**.

## Association

Una volta però identificato il socket destinatario, l'host deve decidere quale protocollo utilizzare per comunicare. 
Dopo ciò l'host sarà a conoscenza : 
- **socket mittente** : il suo indirizzo ip e numero di porta.
- **socket destinatario** : l'indirizzo ip e numero di porta del destinatario.
- **protocollo utilizzato** : UDP o TCP.

Tale processo viene chiamato **association** ed ha lo scopo di identificare in modo univo una connessione all'interno della rete.

## Comunicazione con il server 

Il server crea un "canale virtuale" per instaurare la comunicazione con il nuovo socket e lasciare libero il primo per altre comunicazioni da altri host.

![[Pasted image 20250105205429.png]]
## References

- [[Reti, protocolli e comunicazione]]
- [[Porte Logiche]]
- [[Stream Socket]]
- [[Datagram Socket]]