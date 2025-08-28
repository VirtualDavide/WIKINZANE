2025-06-21 11:39

Tags : [[DailyLinux]]

# Aggiungere un nuovo Font

### Introduzione
Aggiungere un nuovo font su un sistema Linux è un processo relativamente semplice. Puoi farlo scaricando i file del font e copiandoli nella directory appropriata. Questa guida ti mostrerà come installare un font utilizzando il terminale.

### Passaggi per Aggiungere un Font

1. **Scarica il Font**
   - Visita un sito di font come Google Fonts o un altro sito affidabile.
   - Scarica il font in formato .ttf (TrueType Font) o .otf (OpenType Font).

2. **Estrai i File (se necessario)**
   - Se il font è in un file .zip, estrailo utilizzando il comando:
     ```bash
     unzip nome_del_file.zip
     ```

3. **Copia i File del Font**
   - Apri il terminale e utilizza i seguenti comandi per copiare i file del font nella directory dei font di sistema. Sostituisci il percorso con quello corretto della tua cartella:
   ```bash
   # Copia i file del font nella directory dei font di sistema
   sudo cp /percorso/del/font/*.ttf /usr/share/fonts/truetype/
   ```

   - Se hai più formati di font (ad esempio .otf), puoi copiare anche quelli:
   ```bash
   sudo cp /percorso/del/font/*.otf /usr/share/fonts/opentype/
   ```

4. **Aggiorna la Cache dei Font**
   - Dopo aver copiato i file, aggiorna la cache dei font con il seguente comando:
   ```bash
   sudo fc-cache -f -v
   ```

5. **Verifica l'Installazione**
   - Apri un'applicazione di editing di testo o grafica (come LibreOffice, GIMP, ecc.) e controlla se il nuovo font è disponibile nella lista dei caratteri.

### Esempio Pratico

Supponiamo di voler installare i font "Work Sans" e "Asap":

1. Scarica i font da Google Fonts.
2. Estrai i file scaricati.
3. Copia i file dei font:
   ```bash
   sudo cp ~/Scrivania/immagini\ presentazione/Asap/static/*.ttf /usr/share/fonts/truetype/
   sudo cp ~/Scrivania/immagini\ presentazione/Work_Sans/static/*.ttf /usr/share/fonts/truetype/
   ```
4. Aggiorna la cache:
   ```bash
   sudo fc-cache -f -v
   ```
5. Apri LibreOffice e verifica la disponibilità dei font.

### Conclusione
Aggiungere nuovi font su Linux è un processo semplice che può migliorare l'aspetto dei tuoi documenti e presentazioni. Seguendo questi passaggi, puoi facilmente installare e utilizzare qualsiasi font desideri.

## References

- 