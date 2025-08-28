2025-01-13 21:47

Tags : [[PHP]]

# Struttura,Commenti e Variabili (PHP)

All'interno del tuo server Apache, le configurazioni di PHP possono essere modificate tramite il file di configurazione di PHP stesso, che di solito è chiamato `php.ini`.

*salveMondo.php*
```php
/*
author : Giancarlo
data : 2025/01/13
*/

<!DOCTYPE>
<html>
<head>
	<meta charset="UTF-8">
	<title> Salve mondo da PHP </title>
</head>	
<body>
	<?php
		//prima pagine in PHP
		echo "Salve Mondo !"
	?>
</body>
</html>
```

Le istruzioni php sono racchiuse tra i tag **< ?php** e **?>**.  Tali tag servono al server per capire che deve trattare quei codici in maniera differente da del normale codice HTML. Per invocare comunque l'interprete che dovrà decifrare quel testo in istruzioni, si dovrà salvare il file con estensione `.php`.

### Le Variabili 
In PHP una variabile non deve essere preventivamente dichiarata, come succede in altri linguaggi di programmazione come il C, ma è sufficiente inizializzarla a un dato valore per renderla disponibile all'uso all'interno del codice. 

Una Variabile deve iniziare con il simbolo del `$` : 

```php
<?php
	$var = 'Giancarlo'; 
	$VAT = 'Mosca';
	$flag = TRUE;
	$numero = 18;
?>
```

Come si può vedere i nomi delle variabili è **case sensitive** e il loro tipo viene determinato in base al contenuto con cui inizializziamo la variabile.

Per vedere quali tipo di dato è stata assegnato ad una variabile possiamo utilizzare la funzione `gettype` : 

```php
<?php
	$numero = 18;
	echo gettype($numero)
?>
```

*in questo caso la funzione restituirà  : **integer***.
## References

- [[I tipi di variabili, le costanti e le stringhe (PHP)]]