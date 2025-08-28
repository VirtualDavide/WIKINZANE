2025-01-07 23:14

Tags : [[Crittografia]]

# Firma Digitale

La firma digitale è un metodo crittografico che consente principalmente due cose : 

1. **identità** : autenticazione del mittente.
2. **integrità** : i dati non hanno subito mutazioni.

### Crittografia

La firma digitale si basa su un sistema crittografico asimmetrico : 

- **Chiave privata** : Questa chiave è segreta e deve essere mantenuta riservata dal firmatario. Viene utilizzata per firmare digitalmente il documento.
- **Chiave pubblica** : Questa chiave è distribuita e viene usata da chiunque per verificare la firma, proprio perché associata matematicamente alla chiave privata del firmatario.

### Funzionamento 

1. Il documento viene sottoposto ad una **funzione di hash**, che genera un valore univoco del contenuto del documento.
2. Il valore viene quindi **crittografato utilizzando la chiave privata** del firmatario, creando la firma digitale.
3. Il documento originale, insieme alla firma, **viene inviato al destinatario**.
4. Il **destinatario calcola il valore hash** del documento arrivatogli.
5. Utilizzando **la chiave pubblica del firmatario**, il destinatario **decrittografa** la firma digitale per ottenere il valore hash calcolato dal mittente.
6. Se il valore hash calcolato dal destinatario (*4*) corrisponde a quello appena decrittografato, significa che il **documento non è stato alterato** e proviene effettivamente dal firmatario.

## References

- [[Crittografia a chiave asimmetrica]]