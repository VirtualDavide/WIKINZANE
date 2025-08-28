2025-03-06 21:52

Tags : [[ServerSideDevelopment]]

# Scripting-oriented tag

Le **Scripting-oriented tag** sono definite da delimitatori entro cui è presente lo scripting e possono essere classificati : 

**Espressioni**
Le espressioni Java utilizzano dei delimitatori `<%= e %>`. Il risultato di questa viene convertito in una stringa e inserito nella pagina al posto del tag (*le variabili utilizzate nell'espressione sono visibile e vivono solo in quest'ultima*).
```Java
<HTML>
<head>
    <TITLE> Primo codice JSP </TITLE>
</head>
<body>
<p> Ciao la data di oggi e ; <%= new java.util.Date().toString() %> </p>
</body>
</HTML>
```

**Dichiarazioni**
Per dichiarare variabili e metodi si utilizzano i delimitatori `<%! %>` che poi vengono referenziati in qualsiasi punto del codice JSP, richiamandoli all'interno di un espressione.
```Java
<HTML>
<head>
    <TITLE> Esempio di dichiarazione </TITLE>
</head>
<body>
<%!
String utente = "Giancarlo Mosca";
double[] prezzi = {11.5,73.8,90.1};
double getSomma(){
	double a = 2+2.5;
	return a;
}
%>
<p> Ciao sono il cliente <%=utente%> e ho <%=getTotale()%> </p>
</body>
</HTML>
```

**Scriplet**
Nella pagina JSP è possibile inserire frammenti di codice **Java** delimitati da `<% e %>`, che prendono il nome di **scriplet** e possono comprendere istruzioni di controllo per la gestione del flusso di esecuzione del codice.
```Java
<HTML>
<head>
    <TITLE> Esempio di dichiarazione </TITLE>
</head>
<body>
<%!
String utente = "Giancarlo Mosca";
double[] prezzi = {11.5,73.8,90.1};
double getSomma(){
	double a = 2+2.5;
	return a;
}
%>
<p> Ciao sono il cliente <%=utente%> e ho <%=getTotale()%> </p>
<%if (getSomma() > 4){%>
	<p> Ha più di 4 euro</p>
<% } else { %>
	<p> Ha meno di 4 euro</p>
<% } %>	
</body>
</HTML>
```
## References

- [[Tag in una pagina JSP]]
- [[Oggetti Impliciti (JSP)]]
- [[Direttive (JSP)]]