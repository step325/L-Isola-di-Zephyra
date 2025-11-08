# Come Generare i PDF dei Libri

Puoi facilmente creare versioni PDF dei libri direttamente dal tuo browser. Segui questi semplici passaggi:

## Metodo 1: Stampa in PDF dal Browser (Consigliato)

### Per Google Chrome / Microsoft Edge:

1. Apri uno dei file HTML dei libri (es. `book1.html`) nel browser
2. Premi `Ctrl+P` (Windows/Linux) o `Cmd+P` (Mac) per aprire la finestra di stampa
3. Come destinazione, seleziona **"Salva come PDF"**
4. Nelle **Opzioni**:
   - ✅ Grafica di sfondo (per mantenere i colori)
   - Margini: **Predefiniti** o **Minimi**
   - Scala: **Predefinita** (100%)
5. Clicca su **"Salva"**
6. Salva il file nella cartella `docs/assets/pdf/` con il nome appropriato:
   - `Chronicon-Aethyris.pdf`
   - `De-Gentibus-Magicis.pdf`
   - `Il-Cataclisma-del-Nord.pdf`
   - `Teclis-Liberator.pdf`

### Per Firefox:

1. Apri il file HTML nel browser
2. Premi `Ctrl+P` (Windows/Linux) o `Cmd+P` (Mac)
3. Seleziona **"Stampa su file"** o **"Microsoft Print to PDF"**
4. Nelle opzioni:
   - ✅ Stampa sfondi
   - Margini: **Predefiniti**
5. Clicca su **"Stampa"** e salva nella cartella `docs/assets/pdf/`

---

## Metodo 2: Usare uno Strumento Online

Se preferisci, puoi usare un convertitore HTML→PDF online:

### [WeasyPrint](https://weasyprint.org/) (Gratuito, Open Source)

```bash
# Installa WeasyPrint (richiede Python)
pip install weasyprint

# Converti ciascun libro
weasyprint book1.html assets/pdf/Chronicon-Aethyris.pdf
weasyprint book2.html assets/pdf/De-Gentibus-Magicis.pdf
weasyprint book3.html assets/pdf/Il-Cataclisma-del-Nord.pdf
weasyprint book4.html assets/pdf/Teclis-Liberator.pdf
```

### [wkhtmltopdf](https://wkhtmltopdf.org/) (Gratuito, Open Source)

```bash
# Dopo aver installato wkhtmltopdf:
wkhtmltopdf book1.html assets/pdf/Chronicon-Aethyris.pdf
wkhtmltopdf book2.html assets/pdf/De-Gentibus-Magicis.pdf
wkhtmltopdf book3.html assets/pdf/Il-Cataclisma-del-Nord.pdf
wkhtmltopdf book4.html assets/pdf/Teclis-Liberator.pdf
```

---

## Metodo 3: Convertire i File Markdown Originali

Se preferisci partire dai file `.md` originali nella cartella `Biblioteca/`:

### Con Pandoc (Consigliato per qualità professionale):

```bash
# Installa Pandoc: https://pandoc.org/installing.html

# Converti con template PDF elegante
pandoc "Biblioteca/Chronicon Aethyris - Gli Antichi e l'Alba della Magia.md" \
  -o docs/assets/pdf/Chronicon-Aethyris.pdf \
  --pdf-engine=xelatex \
  -V geometry:margin=1in \
  -V fontsize=11pt

# Ripeti per tutti e 4 i libri
```

---

## Nota Importante

Una volta generati i PDF, assicurati che siano salvati in:
```
docs/assets/pdf/
├── Chronicon-Aethyris.pdf
├── De-Gentibus-Magicis.pdf
├── Il-Cataclisma-del-Nord.pdf
└── Teclis-Liberator.pdf
```

I link di download sulla homepage (`index.html`) puntano a questi percorsi specifici.

---

## Suggerimento

**Il metodo più semplice e veloce è il Metodo 1** (Stampa in PDF dal browser). Apri ogni file `bookX.html` in Chrome/Edge, premi Ctrl+P, seleziona "Salva come PDF", abilita "Grafica di sfondo", e salva. Ci vorranno solo 2-3 minuti per tutti e 4 i libri!
