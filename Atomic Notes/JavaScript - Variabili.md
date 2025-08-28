2025-05-30 22:47

Tags : [[JavaScript]]

# JavaScript - Variabili

Le variabili sono come "forzieri" in cui è possibile conservare diversi tipi di dati, come numeri, testi e altro ancora. Per dichiarare una <mark style="background: #BBFABBA6;">variabile</mark>, si possono utilizzare tre principali parole chiave: "var", "let" e "const".

L'utilizzo di "var" è ormai considerato obsoleto, a meno che non si stia scrivendo codice per browser molto datati. Invece, si consiglia di utilizzare "let" per le variabili il cui valore può cambiare nel tempo, e "const" per le variabili il cui valore deve rimanere costante.

Ad esempio, per dichiarare una variabile che rappresenta il prezzo di un prodotto, si potrebbe utilizzare "const":

```javascript
const productPrice = 19.99;
```

Mentre per una variabile che rappresenta il numero di prodotti in un carrello, si potrebbe utilizzare "let":

```javascript
let cartItems = 3;
cartItems = 4; // Il valore della variabile può essere modificato
```


## References

- [[JavaScript - Sintassi]]
- [[JavaScript - var vs let]]