2025-01-13 22:09

Tags : [[PHP]]

# I tipi di variabili, le costanti e le stringhe (PHP)

PHP rende disponibili 8 tipi di **variabili primitive**. 

Quattro tipi semplici : 
1. *boolean;*
2. *integer;*
3. *flot/double;*
4. *string;*

Due tipi composti : 
1. *array;*
2. *object;*

Due tipi speciali : 
1. *resource (utilizzato per rappresentare collegamenti a risorse esterne, come database, file e altre entità.);*
2. *NULL;*

## Le costanti
Le costanti definiscono valori che non cambiano e non possono essere modificati durante l'operazione. Per definire una costante si utilizza la funzione `define()` specificando il nome della costante e il relativo valore : 

```php
<?php
	define("COSTANTE",10);
?>
```

*una costante non deve essere preceduta dal simbolo del `$` come per le altre variabili.*

## Le Stringhe

Una **stringa** è una **concatenazione di caratteri** e può essere definita nei seguenti modi : 

```php
<?php
	$nome = 'Giancarlo';
	$cognome = "Mosca";
?>
```

Il modo più semplice per dichiarare una stringa è utilizzare l'apice singolo `'`, ma se nella parola ce ne fosse già uno, esso deve essere preceduto dal simbolo `\`.  

Se si necessita di concatenare due o più stringhe è possibile utilizzare l'operatore di concatenazione punto `.` (*sono nel caso utilizzassimo i singolo apici*) : 

```php
<?php
	$stringa1 = 'Ciao';
	$stringa2 = 'Mondo';
	echo $stringa1 . $stringa2;
?>
```

Con i doppi apici (`"`), le stringhe vengono automaticamente espanse  e non vi è il bisogno di un operatore di concatenazione.

## References

- [[I tipi di variabili, le costanti e le stringhe (PHP)]]
- [[PHP e Server Web]]
- [[I costrutti di programmazione di PHP]]