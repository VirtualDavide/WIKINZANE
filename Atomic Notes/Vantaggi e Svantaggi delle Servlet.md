2025-01-30 18:22

Tags : [[ServerSideDevelopment]] - [[Java]]

# Vantaggi e Svantaggi delle Servlet

Le tecnologie CGI, oggi sono ancora molto utilizzate. I **vantaggi** più evidenti delle **servlet** rispetto ai programmi CGI sono :
## Vantaggi
1. **Efficienza** : Le servlet vengono istanziate una sola volta in memoria (alla prima invocazione) e sarà poi un thread a gestire al comunicazione tra la servlet ed il suo container, mentre un programma CGI deve essere richiamato ogni volta completamente.
2. **Portabilità** : Le servlet struttano Java e quindi anche i vantaggi di quest'ultimo come la **JVM**.
3. **Persistenza** : Una volta caricata in memoria, mantiene intatte le informazioni, anche per le richieste successive.
4. **Gestione delle sessioni**
## Svantaggi
I principali inconvenienti che denunciano gli sviluppatori sono : 
1. con le servlet si **mescola** la logica di funzionamento dell'applicazione con la sua presentazione.
2. se il codice HTML è complesso **risulta difficile inglobarlo** tramite gli Standard Output.
3. Ogni modifica **richiede una ricompilazione esplicita**.

## References

- [[Servlet]]