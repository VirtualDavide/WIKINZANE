2025-02-12 21:17

Tags : [[VPN]]

# Tunneling e Trasporto

Le modalità di trasporto e tunneling sono due approcci utilizzati nelle VPN (Virtual Private Network) per garantire la sicurezza e la privacy dei dati trasmessi su reti pubbliche. Ecco una spiegazione di ciascuna modalità, come funzionano e le differenze tra di loro.

### Modalità Trasporto

**Cosa è:**
La modalità trasporto è una modalità di funzionamento in cui solo il payload (il contenuto effettivo dei dati) del pacchetto IP viene crittografato. Gli header del pacchetto rimangono intatti e visibili.

**Come funziona:**
1. Quando un pacchetto di dati viene inviato, il contenuto (payload) viene crittografato.
2. L'header del pacchetto, che contiene informazioni come l'indirizzo di origine e di destinazione, rimane non crittografato.
3. Questo consente ai router e ai dispositivi di rete di instradare i pacchetti senza problemi, poiché possono vedere le informazioni di routing.

**Utilizzo:**
La modalità trasporto è comunemente utilizzata in protocolli come l'IPsec (Internet Protocol Security) quando si desidera proteggere le comunicazioni tra due host specifici.

### Modalità Tunneling

**Cosa è:**
La modalità tunneling, al contrario, crittografa l'intero pacchetto IP, inclusi sia il payload che l'header. Questo crea un "tunnel" sicuro attraverso il quale i dati possono viaggiare.

**Come funziona:**
4. Un pacchetto di dati viene incapsulato all'interno di un altro pacchetto IP.
5. L'intero pacchetto originale viene crittografato, compresi gli header.
6. Questo pacchetto crittografato viene quindi inviato attraverso la rete pubblica, dove può viaggiare in modo sicuro fino alla sua destinazione.

**Utilizzo:**
La modalità tunneling è utilizzata in scenari in cui è necessario creare una connessione sicura tra due reti (ad esempio, tra una rete aziendale e un dipendente remoto) e viene comunemente implementata in protocolli come L2TP (Layer 2 Tunneling Protocol) e PPTP (Point-to-Point Tunneling Protocol).

### Differenze tra Modalità Trasporto e Modalità Tunneling

7. **Crittografia:**
   - **Trasporto:** Solo il payload è crittografato; gli header rimangono visibili.
   - **Tunneling:** L'intero pacchetto, inclusi gli header, è crittografato.

8. **Scopo:**
   - **Trasporto:** Utilizzato principalmente per proteggere le comunicazioni tra due host specifici.
   - **Tunneling:** Utilizzato per creare una connessione sicura tra reti diverse.

9. **Visibilità:**
   - **Trasporto:** I router possono vedere gli header e instradare i pacchetti normalmente.
   - **Tunneling:** Gli header sono crittografati, quindi i router non possono vedere le informazioni di routing.

In sintesi, la scelta tra modalità trasporto e tunneling dipende dalle esigenze specifiche di sicurezza e dalla configurazione della rete.
## References

- [[Virtual Private Network]]
- [[La sicurezza nelle VPN]]