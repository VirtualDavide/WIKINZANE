2025-01-23 17:07

Tags : [[HTML]]

# Form e invio dei dati al server

Un **form** è un modulo che ha lo scopo di raccogliere informazioni specifiche inserite dall'utente.

Per inserire un forma all'interno di una pagina we, utilizziamo il tag `<form>` : 

```HTML
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title> PaginaWeb con Form</title>
<head>
<body>
	<form method="post" action="registrazione.php" name="registrazione">
		Nome : <input name="nome" type="text"><br>
		Cognome : <input name="cognome" type="text"><br>
		E-mail : <input name="email" type="text"><br>
		<input value="invia" name="invia" type="submit">
		<input value="cancella" name="cancella" type="reset"> 
	</form>
</body>
</html>
```

All'interno del tag `<form>` sono presenti 3 attributi fondamentali : 
1. **name** : specifica il nome da assegnare a quel modulo.
2. **method** : indica quale protocollo `http` usato dal form.
3. **action** : indica il nome del file che dovrà processare processare i dati inviati dal modulo.
## References

- [[Metodi HTTP]]
- [[Query String]]
- [[Il linguaggio HTML]]