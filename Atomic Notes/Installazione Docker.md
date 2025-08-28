2025-03-23 20:50

Tags : [[Docker]] [[DailyLinux]]

# Installazione Docker

### Nota per l'Installazione di Docker Engine su Ubuntu

#### Prerequisiti

1. **Limitazioni del Firewall**:
   - Se utilizzi `ufw` o `firewalld` per gestire le impostazioni del firewall, ricorda che quando esponi le porte dei container tramite Docker, queste porte bypassano le regole del firewall. Assicurati di configurare correttamente le regole del firewall.
   - Docker è compatibile solo con `iptables-nft` e `iptables-legacy`. Le regole del firewall create con `nft` non sono supportate su un sistema con Docker installato.

2. **Requisiti del Sistema Operativo**:
   - Assicurati di avere una versione a 64 bit di una delle seguenti versioni di Ubuntu:
     - Ubuntu Oracular 24.10
     - Ubuntu Noble 24.04 (LTS)
     - Ubuntu Jammy 22.04 (LTS)
     - Ubuntu Focal 20.04 (LTS)

3. **Disinstallazione di Versioni Precedenti**:
   - Prima di installare Docker Engine, disinstalla eventuali pacchetti in conflitto:
     ```bash
     for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
     ```

#### Installazione di Docker Engine

1. **Imposta il Repository APT di Docker**:
   - Aggiungi la chiave GPG ufficiale di Docker:
     ```bash
     sudo apt-get update
     sudo apt-get install ca-certificates curl
     sudo install -m 0755 -d /etc/apt/keyrings
     sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
     sudo chmod a+r /etc/apt/keyrings/docker.asc
     ```

   - Aggiungi il repository alle sorgenti di APT:
     ```bash
     echo \
       "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
       $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
       sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
     sudo apt-get update
     ```

2. **Installa i Pacchetti di Docker**:
   - Per installare l'ultima versione, esegui:
     ```bash
     sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
     ```

3. **Verifica l'Installazione**:
   - Esegui il comando seguente per verificare che Docker sia stato installato correttamente:
     ```bash
     sudo docker run hello-world
     ```

#### Post-Installazione

- Se ricevi errori quando provi a eseguire Docker senza `sudo`, aggiungi il tuo utente al gruppo `docker`:
  ```bash
  sudo usermod -aG docker $USER
  ```
  Dopo aver eseguito questo comando, esci e accedi nuovamente.

#### Aggiornamento di Docker Engine

- Per aggiornare Docker Engine, segui nuovamente i passaggi per impostare il repository APT e installa la nuova versione desiderata.

#### Disinstallazione di Docker Engine

- Per disinstallare Docker Engine e i pacchetti associati, esegui:
  ```bash
  sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
  ```

- Per rimuovere immagini, container e volumi:
  ```bash
  sudo rm -rf /var/lib/docker
  sudo rm -rf /var/lib/containerd
  ```

- Rimuovi la lista delle sorgenti e le chiavi:
  ```bash
  sudo rm /etc/apt/sources.list.d/docker.list
  sudo rm /etc/apt/keyrings/docker.asc
  ```

Questa nota fornisce una guida completa per l'installazione, l'aggiornamento e la disinstallazione di Docker Engine su Ubuntu. Assicurati di seguire ogni passaggio attentamente per evitare conflitti e problemi di configurazione.
## References

- [[Configurazione di Docker in modalità routless]]