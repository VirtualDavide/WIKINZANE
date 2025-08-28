2025-01-20 09:55

Tags : [[MyLearning/Tags/Firewall]]

# ACL ( Access List Standard )

Un'**ACL** è un file di istruzioni sugli accessi al sistema. Ogni regola **permette o rifiuta l'accesso o l'uscita** nel sistema di eventuali indirizzi ip, protocolli ecc. **Le regole sono sequenziali**, quando un pacchetto arriva al **router** **deve superare tutte le condizioni per entrare o uscire dalla rete**, se solo una di queste non viene soddisfatta il pacchetto viene scartato.

Quando in un router viene registrata una ACL, **questa rallenta le prestazioni delle rete** poiché oltre ad elaborare l'inoltro del pacchetto, deve **anche verificare se può entrare o meno**. L'access list deve essere scritta bene, per non creare troppi rallentamenti.

In questi casi se l'ACL risulta essere pesante per il router, il **controllo dei pacchetti viene affidato ad un server**. Questo permette di liberare risorse di elaborazione al router. 

Su ogni interfaccia **possiamo avere diverse access list**, poiché ogni rete collegata al router, può avere regole diverse di accesso e uscita dalla rete.

**Le ACL standard** possono controllare solo **l'indirizzo ip** mentre le **ACL estese** possono **controllare anche il protocollo**. Per non rallentare troppo la rete, si è stabilito di inserire ACL standard più vicine al destinatario, nell'interfaccia interna al router mentre quelle estese vengono configurante nelle interfacce di uscita del router (*più vicini al mittente*).

Poiché gli indirizzi ip possono essere tanti, possiamo filtrare gli indirizzi per gruppi.

**DMZ** = *Un segmento di rete all'interno di una rete aziendale che ha bisogno di un accesso facilitato al di fuori della rete (server web o mail).*
## References

- 