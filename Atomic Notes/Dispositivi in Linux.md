2024-12-29 19:18

Tags : [[Architettura del sistema]] / [[101.1]]

# Dispositivi in Linux

I dispositivi in linux si differenziano innanzitutto per **cold plug**  e **hot plug**

- **cold plug**: tutti quei dispositivi come schede video, memoria di espansione, pci card ecc...che devono essere montanti a "*freddo*" ovvero solo quando il computer è **spento**.
- **hot plug**: tutti qui dispositivi che possono essere montanti a dispositivo "*caldo*" ovvero a computer **acceso** come USB pen ecc...

*Comandi per controllare i dispositivi collegati* : 
- Il comando `lspci` in Linux è **utilizzato per elencare tutte le periferiche collegate al bus PCI (*Peripheral Component Interconnect*) del sistema**. Questo comando fornisce informazioni dettagliate sulle schede di espansione e sulle periferiche hardware, come schede video, schede di rete, controller USB e altro
	- Aggiungendo `lspci -t` vengono visualizzate le periferiche PCI in una rappresentazione ad albero (tree). Questa opzione mostra la gerarchia delle periferiche PCI, evidenziando le relazioni tra i vari dispositivi e i loro bus, bridge e controller.
- Il comando `lsusb` in Linux è **utilizzato per elencare le periferiche USB collegate al sistema**. Fornisce informazioni sulle porte USB e sui dispositivi connessi, come mouse, tastiere, stampanti, dischi esterni e altri dispositivi USB.

In Linux quasi tutto è gestito come un file e non fanno eccezione i dispositivi. Sotto la cartella `/dev/` infatti sono contenuti dei file che rappresentano le periferiche hardware e i dispositivi virtuali del sistema. Tali file consentono al sistema operativo di interagire con l'hardware.

Dal kernel 2.6 in poi la gestione dei file dei dispositivi viene assegnata ad `udev`, un gestore di dispositivi che crea e rimuove automaticamente i file di dispositivo in base alle periferiche collegate all'hardware esistente.

(le versioni precedenti, necessitavano di avere tutte le voci in `/dev/` già presenti,
*perciò anche quando non erano collegati device, potevamo vedere un interminabile*
elenco di file sotto `/dev/`, anche se vuoti)
## References

- [[Drivers Linux]]
- [[Sys fs]]
- [[D-bus, Hal e Udev]]