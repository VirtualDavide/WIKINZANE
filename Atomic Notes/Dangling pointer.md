2025-08-15 14:31

Tags :

# Dangling pointer

In programmazione, un puntatore pendente o dangling pointer è un puntatore che si riferisce ad un'area di memoria no più valida, perchè già liberata o perchè il puntatore viene utilizzato all'esterno del contesto di esistenza della variabile a cui si riferisce.

Poichè il sistema operativo può riassegnare e riutilizzare quella data locazione di memoria, l'utilizzo di un puntatore pendente porta effetti impredicibili, con conseguente terminazione dell'applicazione che ha causato l'errore, alla corruzione di dati in memoria.

### Alcune cause di dangling pointer
Nei linguaggi di programmazione come il C, che prevedono che sia il programmatore ad occuparsi della liberazione della memoria dinamicamente allocata, i puntatori, come tutte le altre variabili, continuano a contenere l'ultimo valore che è stato loro assegnato, anche quando questo valore non è più valido. Quando ad esempio viene liberata la memoria a cui punt a un certo puntatore, non è più possibile utilizzarlo senza riassegnarlo ad un'altra area di memoria.

Esempio:
```C
int *i = (int *) malloc(sizeof(int));

/* ... */

free(i);

*i = 200;  /* a questo punto il valore contenuto in i non si riferisce più
            * ad un'area di memoria valida!
            */
```

Un'altra causa di danglig pointer, come detto in precedenza, può essere l'utilizzo di un puntatore che riferisce ad una variabile fuori dal contesto di esistenza (*scope*) di quest'ultima.

Esempio:
```C
 int *i = NULL;

  {
    int cont = 3;

    i = &cont;

    /* ... */

    *i = 2;    /* equivale a scrivere cont = 2; */
  }

  *i = 200;  /* a questo punto cont non è più una variabile valida,
              * quindi i non si riferisce più ad un'area di memoria valida!
              */
```

Un ultimo esempio mostra un altro errore che frequentemente causa problemi di puntatori pendenti, ovvero il ritornare, alla fine di una funzione, l'indirizzo di una variabile no più valida al di fuori della funzione stessa.

Esempio: 
```C
  int *ritornaUnInt()
  {
    int cont = 3;

    return &cont;  /* il puntatore a cont non è valido al di fuori di questa funzione! */
  }
```
## References

- 