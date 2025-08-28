2025-01-08 16:23

Tags : [[ServerSideDevelopment]]

# La programmazione lato server

Con il termine **programmazione server-side** viene indicato il meccanismo mediante i quale tutto o parte del documento richiesto dal **client**, e atteso in formato **HTML**, viene generato in seguito ad un'elaborazione che viene eseguita sul **server**, cioè il processo **WebServer** genera dinamicamente la risposta in funzione della richiesta e dei parametri che vengono inclusi in essa.

Il **WebServer** deve essere opportunamente configurato per per generare un contenuto dinamico in base alla sua richiesta. (*ovviamente per far questo abbiamo bisogno di un programma, ed sta proprio in questo la programmazione server-side*)

Possiamo classificare questi programmi per vari aspetti, ma una prima classificazione può essere fatta in base alla *relazione* che hanno i programmi con l'HTML : 

- **codice separato** , associato ad una **URL**:
	- *Common Gateway interface* (**CGI**)
	- *Java servlet*
	- *NSAPI*
- **codice embedded** in HTML :
	- *Server Side Includes* (SSI) - Apache
	- *Active Server Pages* (ASP) - Microsoft
	- *PHP* (Hypertst processor)
	- *Java Server Pages* (JSP)
## References

- [[Common Gateway interface (CGI)]]
- [[Java Servlet]]