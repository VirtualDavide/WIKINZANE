2025-01-30 18:49

Tags : [[ServerSideDevelopment]]

# Sessioni e Cookie

Il protocollo HTTP è **stateless**, cioè dopo una richiesta effettuata dal client e una risposta soddisfatta dal server si riparte da capo.

Per risolvere questo problema possiamo : 

1. Utilizzare **cookie** per "ricordarsi" delle precedenti pagine visitate o dei parametri scelti dall'utente (*le informazioni vengono memorizzate dal client attraverso il browser*).
2. Utilizzare il meccanismo delle **sessioni** (*le informazioni vengono memorizzate sul server*).
## Permanenza dei dati con le sessioni 
Quando il client si collega al server, tramite le servlet è possibile memorizzare le informazioni di nostro interesse.

Alla creazione della sessione **viene assegnato un identificatore univoco**, inviato al client e memorizzato in un cookie.

Ogni richiesta successiva inviata da client, questo trasmette al server l'**ID della sessione** cosichè il server posso riconoscere l'utente e recuperare i dati che ha precedentemente salvato.

Inviando solo l'ID della sessione, si riducono le informazioni scambiate con benefici in termini di sicurezza e efficienza.
## References

- [[Servlet]]