2025-03-06 22:29

Tags : [[ServerSideDevelopment]] [[Java]]

# Oggetti Impliciti (JSP)

Il blocco di codice specificato dalla **scriplet** viene inserito all'interno del metodo `service()` della servlet corrispondentemente generata alla richiesta di esecuzione della pagina JSP (*più precisamente all'interno del metodo **_jspService()** richiamato da **service()***)

Avremo quindi implicitamente a disposizione i seguenti 9 oggetti:

1. **page** : L'oggetto **page** rappresenta l'instanza corrente della servlet : ha come tipo l'interfaccia `HttpjspPage` che discende da `JSPpage`, la quale a sua volta estende la classe servlet e quindi può essere **utilizzata per accedere a tutti i metodi definiti nelle servlet**.

2. **request** : È l'oggetto **HttpServletRequest** che rappresenta la richiesta *Http* che ha portato all'attivazione della pagina **JSP/servlet**. Fornisce i metodi di accesso alla **Request**

3. **response** : È l'oggetto di classe **HttpServletResponse** che rappresenta la risposta **Http** da inviare al client.

4. **out** : È un oggetto che rappresenta il flusso di output su cui viene prodotta la pagina **Web**.

5. **session** : È l'oggetto di classe **HttpSession** che rappresenta la sessione Http sulla quale è stata invocata la pagina : fornisce le informazioni sul contesto di esecuzione della JSP, cioè della sessione corrente di esecuzione per l'utente.

6. **Application** : È un oggetto che fornisce informazioni sul contesto di esecuzione della  JSP e permetti di accedere e di memorizzare gli oggetti per renderli accessibili da qualsiasi utente o da ogni pagina.

7. **pageContext** : rappresenta l'insieme degli oggetti impliciti.

8. **Exception** : Oggetto connesso alla gestione degli errori.

## References

- [[Scripting-oriented tag]]