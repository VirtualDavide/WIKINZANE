2025-03-31 18:26

Tags : [[Firewall]]

# Categorie di Firewall

I firewall si possono distinguere in 3 categorie **in base al livello** dello stack *TCP/IP* in cui operano : 

1. **Application Level Firewall** : In altre parole, valuta il contenuto applicativo dei pacchetti, per esempio riconoscendo o bloccando i dati appartenenti a virus o worm noti in una sessione HTTP o SMTP. A questa categoria appartengono i **proxy**.  Utilizzando un proxy, la configurazione della LAN privata non consente connessioni dirette verso l'esterno : *il proxy è connesso sia alla rete privata sia alla rete pubblica e permette alcune connessioni in modo selettivo*. 
2. **Packet Filter Firewall** : lavora a livello *Network* e a livello *Trasporto*. Esso è molto più veloce dell'Application Firewall poiché controllo solo pochi byte dell'header. Grazie a questa superficialità nel controllo, la rete non subisce rallentamenti rilevanti. I parametri che il *Packet Filter Firewall* controlla nell'header del pacchetto sono : 
	1. *l'indirizzo IP di origine e destinazione*;
	2. *il numero di porta TCP/UDP* *di origine e destinazione*;
	3. *il protocollo di livello superiore utilizzato*;
3. **Stateful Packet Inspection Firewall** : agisce al livello *Trasporto* e permette, oltre al controllo dell'header del pacchetto dati, anche analizzarne il comportamento nel suo contesto. Un firewall di questo tipo di tecnologia può controllare lo stato della connessione TCP e compilare le informazioni ricavate su una tabella. **Questo firewall tiene traccia dello stato delle connessioni attive e analizza i pacchetti in base al contesto della connessione. Può monitorare le sessioni e determinare se un pacchetto fa parte di una connessione già stabilita.**
## References

- [[Firewall - Teoria|Firewall - Teoria]]