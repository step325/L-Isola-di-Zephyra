# 📚 Biblioteca Infinita - Accademia Arcanis

Benvenuto nella **Biblioteca Infinita**, una raccolta digitale di testi antichi sulla storia della magia nel mondo di Warhammer Fantasy Roleplay 4E, creata per la campagna **L'Accademia Arcanis** sull'isola flottante di Zephyra.

---

## 📖 I Libri della Biblioteca

Questa biblioteca contiene quattro tomi fondamentali per ogni studente di magia:

### 1. **Chronicon Aethyris: Gli Antichi e l'Alba della Magia**
- **Autore:** Magister Alaric von Strassburg, Collegio Bianco di Altdorf
- **Argomento:** Le radici della magia - Gli Antichi, gli Slann, l'Aethyr e le Pietre Guardiane

### 2. **De Gentibus Magicis: L'Eredità Arcana delle Razze del Vecchio Mondo**
- **Autore:** Magister Eleonora Stahl, Collegio di Giada
- **Argomento:** L'eredità magica di Elfi, Nani e Umani - tre filosofie a confronto

### 3. **Il Cataclisma del Nord: Cronache della Caduta dei Portali**
- **Autore:** Maestro Heinrich Kemmler III
- **Argomento:** La Caduta dei Portali del Caos, la nascita del Dhar e degli Otto Venti *[Consultazione Ristretta]*

### 4. **Teclis Liberator: Il Dono degli Alti Elfi e la Fondazione dei Collegi**
- **Autore:** Maestro Balthazar Volker, Patriarca Supremo dei Collegi di Magia
- **Argomento:** Sigmar, Magnus il Pio, Teclis e la fondazione degli Otto Collegi di Magia

---

## 🌐 Pubblicare il Sito su GitHub Pages

Segui questi passaggi per rendere la Biblioteca accessibile online gratuitamente:

### Passo 1: Crea un Repository su GitHub

1. Vai su [github.com](https://github.com) e accedi (o crea un account gratuito)
2. Clicca su **"New repository"** (+ in alto a destra → New repository)
3. Imposta:
   - **Nome repository:** `biblioteca-arcanis` (o un nome a tua scelta)
   - **Descrizione:** "Biblioteca Infinita dell'Accademia Arcanis - WFRP 4E"
   - **Visibilità:** Public (o Private se preferisci, ma Pages funziona meglio con Public)
   - ✅ Seleziona **"Add a README file"**
4. Clicca su **"Create repository"**

### Passo 2: Carica i File

#### Opzione A: Upload via Web (più semplice)

1. Nel tuo repository appena creato, clicca su **"Add file"** → **"Upload files"**
2. Trascina l'intera cartella `docs/` (tutti i file HTML, CSS, ecc.)
3. Scrivi un messaggio di commit (es. "Aggiunge Biblioteca Infinita")
4. Clicca su **"Commit changes"**

#### Opzione B: Upload via Git (più avanzato)

```bash
# Apri un terminale nella cartella Avventura
cd "/mnt/c/Users/stefa/Desktop/Avventura"

# Inizializza git se non l'hai già fatto
git init
git add docs/
git commit -m "Aggiunge Biblioteca Infinita"

# Collega al tuo repository GitHub (sostituisci USERNAME e REPO)
git remote add origin https://github.com/USERNAME/biblioteca-arcanis.git
git branch -M main
git push -u origin main
```

### Passo 3: Attiva GitHub Pages

1. Nel tuo repository su GitHub, vai su **"Settings"** (Impostazioni)
2. Nella barra laterale sinistra, clicca su **"Pages"**
3. Sotto **"Source"** (Sorgente):
   - Branch: seleziona **`main`** (o `master`)
   - Folder: seleziona **`/docs`**
4. Clicca su **"Save"**
5. Dopo qualche minuto, GitHub ti darà un URL:
   ```
   https://[tuo-username].github.io/biblioteca-arcanis/
   ```

### Passo 4: Condividi con i Giocatori!

Ora puoi condividere l'URL con i tuoi giocatori. Potranno:
- Navigare la biblioteca direttamente dal browser
- Leggere i libri online con un design immersivo
- Scaricare i PDF (una volta generati - vedi sotto)

---

## 📥 Generare i PDF

I link di download PDF sulla homepage puntano a file che devi ancora creare. Segui le istruzioni in [`GENERA_PDF.md`](GENERA_PDF.md) per creare i PDF.

**Metodo più semplice:**
1. Apri `book1.html` in Chrome/Edge
2. Premi `Ctrl+P` (Stampa)
3. Seleziona "Salva come PDF"
4. Abilita "Grafica di sfondo"
5. Salva in `docs/assets/pdf/Chronicon-Aethyris.pdf`
6. Ripeti per book2, book3, book4

Una volta creati i PDF, caricali su GitHub nella cartella `docs/assets/pdf/`.

---

## 🎨 Design e Tematica

Il sito web è ispirato all'estetica dell'**Accademia Arcanis** e dell'**isola flottante di Zephyra**:

### Color Palette
- **Sfondo:** Gradiente blu-viola nebuloso (cielo di Zephyra)
- **Accenti:** Oro e argento (magia luminosa)
- **Otto Venti della Magia:**
  - 🔴 Aqshy (Fuoco) - Rosso
  - 🔵 Azyr (Empireo) - Blu
  - 🟡 Chamon (Metallo) - Oro
  - 🟤 Ghur (Bestie) - Ambra
  - 🟢 Ghyran (Vita) - Verde
  - ⚪ Hysh (Luce) - Bianco
  - 🟣 Shyish (Morte) - Viola
  - ⚫ Ulgu (Ombre) - Grigio

### Elementi Visivi
- **Effetto nebuloso animato** (richiama le nuvole incantate di Zephyra)
- **Cristalli luminosi** con animazione pulsante
- **Scaffali virtuali** con effetto hover magico
- **Rune decorative** (alfabeto runico nanico/elfico)
- **Font eleganti:** Cinzel (titoli), Crimson Text (corpo)

### Atmosfera
- Majestuosa ma accessibile
- Magica senza essere kitsch
- Leggibile e professionale
- Responsive (funziona su mobile)

---

## 🛠️ Struttura dei File

```
docs/
├── index.html              # Homepage - scaffale biblioteca
├── book1.html              # Chronicon Aethyris
├── book2.html              # De Gentibus Magicis
├── book3.html              # Il Cataclisma del Nord
├── book4.html              # Teclis Liberator
├── css/
│   └── style.css           # Tutti gli stili tematici
├── assets/
│   └── pdf/                # PDF scaricabili (da generare)
│       ├── Chronicon-Aethyris.pdf
│       ├── De-Gentibus-Magicis.pdf
│       ├── Il-Cataclisma-del-Nord.pdf
│       └── Teclis-Liberator.pdf
├── README.md               # Questo file
└── GENERA_PDF.md           # Istruzioni per creare i PDF
```

---

## 🎮 Per i Giocatori

Se sei un giocatore della campagna **L'Accademia Arcanis**, benvenuto! Questi tomi contengono conoscenza essenziale per comprendere:
- Le origini della magia nel Vecchio Mondo
- Il debito dell'umanità verso gli Alti Elfi
- I pericoli del Dhar (magia corrotta)
- La storia degli Otto Collegi di Magia

**Ricorda:**
> *"Il sapere è potere, ma il potere mal gestito conduce sempre alla rovina."*

L'uso del **Dhar** è proibito sotto pena di morte. Questi testi ti insegnano a riconoscerlo e combatterlo, non a praticarlo.

---

## 📝 Crediti

- **Ambientazione:** L'Accademia Arcanis, Isola di Zephyra
- **Sistema di gioco:** Warhammer Fantasy Roleplay 4th Edition (WFRP 4E)
- **Autore contenuti:** [Il tuo nome]
- **Anno:** 2512 IC (2025 AD)

### Tecnologie Utilizzate
- HTML5
- CSS3 (animazioni, gradients, flexbox/grid)
- Google Fonts (Cinzel, Crimson Text)
- GitHub Pages (hosting gratuito)

---

## 🔮 Note Tecniche

### Compatibilità Browser
Il sito è ottimizzato per:
- ✅ Google Chrome / Microsoft Edge (consigliato)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (responsive design)

### Animazioni
Se le animazioni causano problemi di performance, puoi disabilitarle aggiungendo al CSS:

```css
* {
    animation: none !important;
}
```

### Personalizzazione
Puoi modificare i colori editando le variabili CSS in `css/style.css`:

```css
:root {
    --academy-bg: ...
    --academy-primary: ...
    /* ecc. */
}
```

---

## 📧 Supporto

Se hai problemi con GitHub Pages o il sito, controlla:
1. Che tutti i file siano nella cartella `docs/`
2. Che GitHub Pages sia configurato su branch `main` e folder `/docs`
3. Che i link relativi siano corretti (es. `css/style.css` non `/css/style.css`)

---

## ⚔️ Licenza

Questo progetto è creato per uso personale nella campagna di WFRP 4E.

**Warhammer Fantasy Roleplay** è proprietà di Games Workshop e Cubicle 7 Entertainment.

---

**Que il sapere illumini il tuo cammino, ma mai ti acciechi.**

*— La Biblioteca Infinita, Anno 2512 IC*