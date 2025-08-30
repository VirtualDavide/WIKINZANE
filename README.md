# 🌌 WIKINZANE – dagli studenti, per gli studenti 💥

## 📖 Descrizione del progetto

**WIKINZANE** è un’enciclopedia collaborativa creata su **[Obsidian](https://obsidian.md/)**.
Il suo scopo è semplice: mettere insieme appunti, note, approfondimenti e strumenti utili **per imparare meglio**, condivisi da studenti e curiosi.
Non è una Wikipedia tradizionale, ma un progetto aperto e collaborativo, in costante evoluzione.

---

## 👥 Ideatori del progetto

* [Feb487 (Mosca Giancarlo)](https://github.com/Feb487)
* [VirtualDavide (Longo Davide)](https://github.com/VirtualDavide)

---

## ⚙️ Requisiti per partecipare al progetto

* [Git](https://git-scm.com/downloads)
* Un account [GitHub](https://github.com/)
* [Obsidian](https://obsidian.md/#utm_source=chatgpt.com) ➝ [Tutorial Markdown (YouTube Playlist)](https://youtube.com/playlist?list=PL3NaIVgSlAVLHty1-NuvPa9V0b0UwbzBd&si=lJTjmGODGxnn396i)
* Conoscenze (anche minime) di **Markdown**
* Una distro Linux basata su **Debian**, **Red Hat**, **Arch Linux**, oppure **Windows 10/11**

---

## 🌀 Cos’è Git?

**[Git](https://git-scm.com/downloads)** è un sistema di controllo di versione distribuito. Permette di tenere traccia delle modifiche a un progetto, lavorare in team e coordinarsi senza rischiare di perdere dati.

---

## 🗂 Cos’è Obsidian?

**[Obsidian](https://obsidian.md/#utm_source=chatgpt.com)** è un’app per note basata su **Markdown**, pensata per creare collegamenti e reti di conoscenza. È perfetta per creare un “wiki personale” o, come in questo caso, una **enciclopedia collaborativa**.

---

## 🔧 Installazione Git

### Debian / Ubuntu

```bash
sudo apt update
sudo apt install git
```

### Red Hat / Fedora

```bash
sudo dnf install git
```

### Arch Linux

```bash
sudo pacman -S git
```

### Windows 10/11

Scarica e installa [Git per Windows](https://git-scm.com/download/win).

---

## 🔧 Installazione Obsidian

### Debian / Ubuntu

Scarica il `.deb` dal sito ufficiale:

```bash
wget https://github.com/obsidianmd/obsidian-releases/releases/download/v1.6.7/obsidian_1.6.7_amd64.deb
sudo dpkg -i obsidian_1.6.7_amd64.deb
```

### Red Hat / Fedora

Scarica il `.rpm` dal sito ufficiale:

```bash
sudo rpm -i obsidian-1.6.7.rpm
```

### Arch Linux

Obsidian è disponibile su AUR:

```bash
yay -S obsidian
```

### Windows 10/11

Scarica l’installer ufficiale da [qui](https://obsidian.md/).

---

## 📂 Struttura del progetto

Il progetto è strutturato in 6 cartelle principali:

* **Index** → contiene gli indici che collegano i contenuti principali e i tag.
* **Tags** → contiene le tag che collegano le note agli index.
* **Atomic Notes** → note pronte, complete e collegate ai tag.
* **Raw Notes** → bozze o note non ancora finite.
* **Excalidraw** → note disegnate con il plugin *Excalidraw*.
* **Templates** → modelli di note da usare con **CTRL + T** in Obsidian.

⚠️ **IMPORTANTE**: non eliminare mai i seguenti file/cartelle:

* `INDEX - THE BIG BANG 💥🌌`
* `TAGS - THE BIG BANG 💥🌌`
* `ATOMIC NOTES - THE BIG BANG 💥🌌`
* `RAW NOTES - THE BIG BANG 💥🌌`
* `DRAWING - THE BIG BANG 💥🌌`
* La cartella **Templates** con tutto il suo contenuto.

---

## 🚀 Come addentrarsi nel progetto

Clona il repository:

### HTTPS

```bash
git clone https://github.com/WIKIZANE.git
```

### SSH

```bash
git clone git@github.com:VirtualDavide/WIKIZANE.git
```

Entra nella cartella:

```bash
cd WIKIZANE
```

Crea un **branch** prima di iniziare a lavorare:

```bash
git checkout -b feature-nome-feature
```

👉 Un **branch** è una “copia” del progetto principale dove puoi lavorare senza modificare subito il **main**.

---

## 🗂 Configurazione Templates in Obsidian

1. Vai su **Impostazioni > Templates > "Template folder location"**.
2. Seleziona la cartella:

   ```
   WIKINZANE - Templates
   ```
3. Vai su **Impostazioni > Hotkeys**.
4. Cerca:

   ```
   Templates: Insert Template
   ```
5. Imposta la hotkey su **CTRL + T**.

---

## ✍️ Come contribuire

Entra nella cartella:

```bash
cd WIKINZANE
```

Crea un **branch** prima di iniziare a lavorare:

```bash
git checkout -b feature-nome-feature
```

👉 Un **branch** è una “copia” del progetto principale dove puoi lavorare senza modificare subito il **main**.

* **Creare un Index** → se servono nuovi collegamenti per più tag.
* **Creare un Tag** → se servono nuove categorie da collegare a index e note.
* **Creare una Raw Note** → per bozze non finite o in lavorazione.
* **Creare una Atomic Note** → per contenuti già pronti e completi.
* **Creare un Excalidraw** → per aggiungere disegni o schemi grafici.

⚠️ Non creare file fuori dalle cartelle già esistenti e **non toccare la cartella Templates**.

---

## 📤 Come inviare le modifiche

Aggiungi i file al commit:

```bash
git add .
```

Crea un commit con la descrizione delle modifiche:

```bash
git commit -m "Descrizione delle modifiche"
```

Invia il branch remoto su GitHub:

```bash
git push origin feature-nome-feature
```

Poi apri una **Pull Request** su GitHub.
Gli admin (Feb487 e VirtualDavide) approveranno o meno la modifica.

### 🗑️ Eliminare un branch dopo la Pull Request accettata

Torna sul branch principale:

```bash
git checkout main
```

Elimina il branch in locale:

```bash
git branch -d feature-nome-feature
```

Elimina il branch anche su GitHub:

```bash
git push origin --delete feature-nome-feature
```

---

## 🔄 Come aggiornare il progetto

Torna sul branch principale:

```bash
git checkout main
```

Scarica le ultime modifiche dal repository principale:

```bash
git pull origin main
```

Torna al tuo branch di lavoro:

```bash
git checkout feature-nome-feature
```

Unisci le modifiche dal main:

```bash
git merge main
```

---

## 🥚 EasterEgg

* Dentro **Raw Notes**, nel file `RAW NOTES - THE BIG BANG 💥🌌` puoi aggiungere:

  ```
  [nickname-github](link-profilo-github) - frase personalizzata
  ```

* Dentro **Excalidraw**, nel file `DRAWING - THE BIG BANG 💥🌌` puoi aggiungere un disegno (⚠️ sarà controllato prima di unirlo al progetto principale).

---

## 📬 Contatti

* [VirtualDavide](https://github.com/VirtualDavide)
* [Feb487](https://github.com/Feb487)

Per domande, suggerimenti o collaborazioni:

* Apri una **Issue** su GitHub
* Usa la sezione **Discussioni** del progetto

---

## 💖 Donazioni

Se vuoi supportare il progetto, puoi contribuire tramite [GitHub Sponsors](https://github.com/sponsors) o altri canali che aggiungeremo presto.

---
