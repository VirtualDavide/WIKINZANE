2025-01-03 11:41

Tags : [[Linux LPI - 101]]

# Unita,stato e preset

- **UNIT FILE**: Questa colonna mostra il nome del file di unità. 
- **STATE**:  Questa colonna indica lo stato attuale dell'unità di servizio in relazione alla sua configurazione. Gli stati comuni includono:
- **PRESET**: Questa colonna mostra la configurazione predefinita dell'unità di servizio, come è stata impostata dal pacchetto software o dalla configurazione di sistema.
    
Ecco un elenco con una breve e precisa definizione di ciascuno stato delle unità di servizio in systemd:

1. **enabled**: Il servizio è abilitato per l'avvio automatico all'avvio del sistema.
    
2. **disabled**: Il servizio è disabilitato e non verrà avviato automaticamente all'avvio del sistema.
    
3. **static**: Il servizio non può essere abilitato o disabilitato direttamente; viene avviato automaticamente in risposta a un'altra unità di servizio specifica.
    
4. **masked**: Il servizio è "mascherato" e non può essere avviato, nemmeno manualmente. Questo stato è utilizzato per prevenire l'avvio accidentale del servizio.
    
5. **generated**: Il servizio è stato generato automaticamente da un altro processo, come un generatore di unità, e non è stato creato manualmente dall'utente.
    
6. **failed**: Il servizio ha fallito durante l'avvio o l'esecuzione, indicando che ci sono stati problemi con il servizio.
    
9. **alias**: L'unità di servizio è un alias per un'altra unità, consentendo di riferirsi a quest'ultima con un nome alternativo.
    
10. **indirect**: Il servizio non è direttamente abilitato o disabilitato, ma può essere avviato automaticamente in risposta a più unità abilitati.
## References

- [[Runlevel e Demoni]]