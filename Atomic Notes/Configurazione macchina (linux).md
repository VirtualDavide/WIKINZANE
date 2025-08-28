2024-12-21 12:42

Tags :

# Configurazione macchina (linux)

Una volta creata la macchina e scelto il sistema operativo che dovrà essere visualizzato, andare nella sezione impostazioni (selezionare la modalità esperto o avanzate) : 

- **Sistema**
	1. **Memoria di Base** : La memoria di base è la RAM che andrà a mangiare il sistema operativo virtualizzato al suo avvio.
	2. **Chipset** : Il chipset è il responsabile della comunicazione tra il processore e le altre componenti del PC, come la memoria, le schede grafiche, le unità di archiviazione ecc.
		1. ICH9 : chipset intel, moderno e prestante, progettato per i processori intel series 3 (scelta consigliata).
		2. PIIX3 : chipset intel, ma molto più vecchio, sviluppato per i processori celeron, pentiuam ecc.
	3. **Funzionalità estese** : 
		1. Abilità EFI : versione superiore del BIOS, consigliata la sua attivazione se si vuole virtualizzare sistemi operativi moderni.
- **Schermo**
	1. **Memoria video** : assegnare tutti e 128 MB di memoria.
	2. **Funzionalità estese** : Abilitare l'accelerazione 3D per una migliore visualizzazione del sistema virtualizzato, specialmente se moderno.	 
- **Rete**
	1. **Connessa a** : Di default, l'opzione attivata è quella del **NAT**, tale però darà un indirizzamento diverso da quello a cui è connesso il nostro pc, rendendo irraggiungibile la macchina nelle rete locale. Selezionare quindi l'opzione "*Scheda con Bridge*". Questa permetterà alla nostra macchina virtuale di essere raggiungibile, avendo un indirizzo ip della nostra rete locale.

## References

- [[VirtualBox]]