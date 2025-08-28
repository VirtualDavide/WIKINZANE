2025-01-08 16:38

Tags : [[ServerSideDevelopment]]

# Common Gateway interface (CGI)

Le applicazioni che utilizzano questo standard prendono il nome di **programma CGI** e sono scritte in qualunque linguaggio di programmazione che può leggere da *standard input* e scrivere su *standard output*, come Python,Perl,C,C++.

Un **programma CGI** viene eseguito dinamicamente in risposta ad una richiesta Http.

Le operazioni si sviluppano nel seguente ordine :
1. Il client comunica al server di voler utilizzare un programma CGI
2. il server attraverso l'interfaccia CGI, il server chiama il programma richiesto dal client e gli passa i parametri presi per esempio da un form.
3. Il programma CGI elabora i dati e li comunica al server tramite una pagina HTML.
4. Il server invia al client i dati elaborati dal programma sempre tramite protocollo http.

Sostanzialmente in base alle richieste, il programma crea la pagina HTML ed il WebServer la invia al client.
## References

- [[Apache server]]
- [[Servlet]]