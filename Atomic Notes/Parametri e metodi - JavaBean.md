2025-03-09 20:15

Tags : [[Java]] [[ServerSideDevelopment]]

# Parametri e metodi - JavaBean

### Parametri nei delimitatori JSP
Quando utilizzi il tag `<jsp:useBean>`, puoi specificare diversi attributi:

 **`id`**: Questo è il nome dell'istanza del bean che verrà utilizzata nella pagina JSP. È un identificatore che consente di accedere al bean.
```Java
<jsp:useBean id="user" class="com.example.User" />
```

**`class`**: Specifica il nome completo della classe del bean, inclusi il pacchetto e il nome della classe. Questo è necessario per creare un'istanza del bean.
```Java
<jsp:useBean id="user" class="com.example.User" />
```

**`scope`**: Definisce l'ambito in cui il bean sarà disponibile. Gli ambiti comuni includono:
- **`page`**: Il bean è disponibile solo nella pagina corrente.
- **`request`**: Il bean è disponibile per la durata della richiesta HTTP.
- **`session`**: Il bean è disponibile per tutta la durata della sessione dell'utente.
- **`application`**: Il bean è disponibile per tutta l'applicazione web.
```Java
<jsp:useBean id="user" class="com.example.User" scope="session" />
```

### Proprietà e metodi getter/setter
Le proprietà di un JavaBean sono rappresentate da variabili di istanza (attributi) e sono accessibili tramite metodi getter e setter. Ecco come funziona:

- **Proprietà**: Sono le variabili di istanza della classe. Ad esempio, nel bean `User`, abbiamo le proprietà `name` e `age`.
    
- **Metodi getter**: Sono utilizzati per recuperare il valore di una proprietà. Il nome del metodo getter segue la convenzione `getNomeProprietà()`. Ad esempio, per la proprietà `name`, il metodo getter sarà `getName()`.
    
- **Metodi setter**: Sono utilizzati per impostare il valore di una proprietà. Il nome del metodo setter segue la convenzione `setNomeProprietà()`. Ad esempio, per la proprietà `name`, il metodo setter sarà `setName(String name)`.

### *Esempio*
![[JavaBeanDB.pdf]]
## References

- [[JavaBean]]