# Guida: Creazione Nuovi Anelli per il Sito

Questa guida spiega come creare nuovi anelli di Zephyra seguendo il pattern standardizzato unificato implementato per Anello di Bronzo e Anello d'Argento.

---

## 📋 Pattern Standardizzato Unificato

### Struttura Base Identica per Tutti gli Anelli

A partire da gennaio 2025, **tutti gli anelli utilizzano la stessa struttura standardizzata**:

- **Struttura quartieri/distretti:** Ogni quartiere/distretto ha esattamente **4 file HTML**:
  - `index.html` - Panoramica con 3 card di navigazione (👥⚡🏛️)
  - `npc.html` - **Abitanti Noti** (PNG caratterizzati)
  - `hook.html` - **Hook per Avventure** (semi di storie)
  - `caratteristiche.html` - **Caratteristiche** (luoghi, atmosfera, pericoli)

- **Navigazione con emoji:** Ogni index.html mostra 3 card:
  - 👥 **Abitanti Noti** - NPC del quartiere
  - ⚡ **Hook per Avventure** - Semi narrativi
  - 🏛️ **Caratteristiche** - Luoghi e atmosfere

- **Sezioni opzionali** sulla landing page dell'anello:
  - `locations/` - Luoghi importanti (file HTML individuali)
  - `organizzazioni/` - Fazioni e organizzazioni (file HTML individuali)
  - `extra/` - Sezioni aggiuntive (vita-quotidiana.html, eventi-ricorrenti.html, tensioni.html)

### Esempi Implementati

**Anello di Bronzo:**
- 8 Distretti (4 file ciascuno = 32 file)
- 10 Locations importanti
- 5 Organizzazioni
- 3 Extra (vita quotidiana, eventi, tensioni)
- **Totale:** ~50 file

**Anello d'Argento:**
- 8 Quartieri (4 file ciascuno = 32 file)
- 10 Locations importanti
- 1 Organizzazione principale (Gilda Artisti)
- 3 Extra (vita quotidiana, eventi, tensioni)
- **Totale:** ~46 file

---

## 📁 Struttura Directory Standard

```
docs/ambientazione/
├── anelli/
│   └── anello-{nome}.html           # Landing con sezioni multiple
└── distretti/anello-{nome}/
    ├── {nome-distretto}/             # Per Bronzo (struttura piatta)
    │   ├── index.html                # Panoramica + 3 card (👥⚡🏛️)
    │   ├── npc.html                  # Abitanti Noti
    │   ├── hook.html                 # Hook per Avventure
    │   └── caratteristiche.html      # Caratteristiche e luoghi
    ├── quartieri/                    # Per Argento (cartella quartieri)
    │   └── {nome-quartiere}/
    │       ├── index.html            # Panoramica + 3 card (👥⚡🏛️)
    │       ├── npc.html              # Abitanti Noti
    │       ├── hook.html             # Hook per Avventure
    │       └── caratteristiche.html  # Caratteristiche e luoghi
    ├── locations/                    # OPZIONALE - luoghi importanti
    │   └── {nome-location}.html      # Pagina completa location
    ├── organizzazioni/               # OPZIONALE - fazioni
    │   ├── index.html                # Panoramica organizzazioni
    │   └── {nome-org}.html           # Pagina organizzazione
    └── extra/                        # OPZIONALE - contenuti aggiuntivi
        ├── vita-quotidiana.html      # Ciclo giornaliero, economia
        ├── eventi-ricorrenti.html    # Festività e celebrazioni
        └── tensioni.html             # Conflitti e tensioni sociali
```

---

## 🧭 Navigazione Standard

### Struttura Card di Navigazione (index.html)

Ogni quartiere/distretto deve avere esattamente **3 card** con emoji tematiche:

```html
<section class="library-shelf">
    <!-- Card 1: Abitanti Noti -->
    <a href="npc.html" class="book-card {classe-css}">
        <div class="book-icon">👥</div>
        <h2>Abitanti Noti</h2>
        <p class="author">{Sottotitolo Specifico}</p>
        <p class="description">
            {Descrizione NPC principali}
        </p>
    </a>

    <!-- Card 2: Hook per Avventure -->
    <a href="hook.html" class="book-card {classe-css}">
        <div class="book-icon">⚡</div>
        <h2>Hook per Avventure</h2>
        <p class="author">Semi di Storie</p>
        <p class="description">
            {Descrizione hook principali}
        </p>
    </a>

    <!-- Card 3: Caratteristiche -->
    <a href="caratteristiche.html" class="book-card {classe-css}">
        <div class="book-icon">🏛️</div>
        <h2>Caratteristiche</h2>
        <p class="author">Luoghi e Atmosfere</p>
        <p class="description">
            {Descrizione luoghi distintivi}
        </p>
    </a>
</section>
```

### Pulsanti di Navigazione tra Quartieri/Distretti

**FONDAMENTALE:** Ogni `index.html` di quartiere/distretto deve avere **3 pulsanti di navigazione**:

```html
<div class="navigation">
    <a href="../{distretto-precedente}/index.html" class="btn nav-button">← Distretto Precedente: {Nome}</a>
    <a href="../../anelli/anello-{nome}.html" class="btn nav-button">Torna all'Anello {Nome}</a>
    <a href="../{distretto-successivo}/index.html" class="btn nav-button">Prossimo Distretto: {Nome} →</a>
</div>
```

**Path corretti per il pulsante centrale:**
- **Anello di Bronzo** (struttura piatta): `../../anelli/anello-di-bronzo.html`
- **Anello d'Argento** (cartella quartieri): `../../../../anelli/anello-d-argento.html`

**Eccezioni:**
- **Primo distretto:** Solo pulsante centrale + pulsante "Prossimo →"
- **Ultimo distretto:** Solo pulsante "← Precedente" + pulsante centrale

---

## 📝 Template Landing Page

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="L'Anello {Nome} - {Motto}">
    <title>L'Anello {Nome} - Accademia Arcanis</title>
    <link rel="stylesheet" href="../../css/style.css">
</head>
<body>
    <header>
        <h1>
            <a href="../../index.html" class="home-icon" title="Torna alla Home">🏠</a>
            L'Anello {Nome}
        </h1>
        <p class="subtitle">{Motto/Sottotitolo}</p>
        <p class="custode">{Descrizione popolazione}</p>
    </header>

    <main>
        <section class="intro">
            <p>{Introduzione narrativa 2-3 paragrafi}</p>
            <em>"{Citazione caratteristica}"</em>
        </section>

        <!-- SEZIONE OBBLIGATORIA: Quartieri/Distretti -->
        <section class="library-shelf">
            <!-- 8 carte quartieri con emoji distintive -->
            <a href="../distretti/anello-{nome}/{distretto}/index.html" class="book-card {classe}">
                <div class="book-icon">{emoji}</div>
                <h2>{Nome Distretto}</h2>
                <p class="author">{Motto Distretto}</p>
                <p class="description">{Descrizione breve}</p>
            </a>
            <!-- Ripetere per tutti i quartieri/distretti -->
        </section>

        <!-- SEZIONE OPZIONALE: Luoghi Importanti -->
        <h2 class="section-title">Luoghi Importanti</h2>
        <section class="library-shelf">
            <!-- N carte locations -->
        </section>

        <!-- SEZIONE OPZIONALE: Organizzazioni e Fazioni -->
        <h2 class="section-title">Organizzazioni e Fazioni</h2>
        <section class="library-shelf">
            <!-- N carte organizzazioni -->
        </section>

        <!-- SEZIONE OPZIONALE: Vita e Cultura -->
        <h2 class="section-title">Vita e Cultura</h2>
        <section class="library-shelf">
            <!-- 3 carte: vita quotidiana, eventi, tensioni -->
        </section>
    </main>

    <footer>
        <p>Anno 2512 IC - Accademia Arcanis</p>
        <p><em>"{Citazione finale}"</em></p>
    </footer>
</body>
</html>
```

---

## 📄 Template Pagine Standard

### Template: npc.html (Abitanti Noti)

```html
<div class="book-content">
    <h2>{Nome NPC}</h2>
    <p><strong>Razza:</strong> {Razza} | <strong>Età:</strong> {Età}</p>
    <p>
        {Descrizione fisica e background - 2-3 paragrafi}
    </p>
    <p>
        <strong>Personalità:</strong> {Tratti caratteriali, motivazioni, segreti}
    </p>

    <hr>

    <!-- Ripetere per 3-5 NPC per quartiere -->
</div>
```

### Template: caratteristiche.html

```html
<h2>📍 Descrizione Generale</h2>
<p>{2-3 paragrafi descrittivi con dettagli sensoriali}</p>

<h2>🏛️ Luoghi Distintivi</h2>

<h3>{Emoji} {Nome Luogo 1}</h3>
<p>{Descrizione dettagliata}</p>

<h3>{Emoji} {Nome Luogo 2}</h3>
<p>{Descrizione dettagliata}</p>

<!-- 3-5 luoghi totali -->

<h2>🎭 Atmosfera del Quartiere</h2>
<p>{Descrizione immersiva: suoni, odori, sensazioni}</p>

<h2>⚠️ Pericoli del Quartiere</h2>
<p>{Minacce, rischi, cosa può andare storto}</p>
```

### Template: hook.html

```html
<h2>⚡ Hook 1: {Titolo Hook}</h2>
<p><strong>Tipo:</strong> {Investigazione/Combattimento/Sociale/etc.}</p>
<p>{Descrizione hook - problema, aggancio per i PG}</p>

<h3>💀 Difficoltà e Prove</h3>
<table>
    <thead>
        <tr>
            <th>Azione</th>
            <th>Abilità</th>
            <th>Difficoltà</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>{Azione}</td>
            <td>{Abilità WFRP}</td>
            <td>{Facile/Media/Difficile/Molto Difficile}</td>
        </tr>
        <!-- 4-6 righe -->
    </tbody>
</table>

<h3>🎲 Possibili Sviluppi</h3>
<ul>
    <li>{Esito 1}</li>
    <li>{Esito 2}</li>
    <li>{Complicazione}</li>
</ul>

<hr>

<!-- Ripetere per 3-5 hook totali -->
```

---

## 🎨 CSS: Aggiungere Tema Colore

### 1. Definire Variabili Colore

In `docs/css/style.css`, aggiungere nella sezione `:root`:

```css
/* Anello {Nome} Theme */
--accent-{nome}: #{colore-hex};
--accent-{nome}-alt: #{colore-alternativo};
--border-{nome}: rgba({r}, {g}, {b}, 0.2);
```

**Esempi:**
- Bronzo: `--accent-bronze: #cd7f32;`
- Argento: `--accent-silver: #c0c0c0;`
- Oro: `--accent-gold: #ffd700;`

### 2. Creare Classi CSS

```css
/* ==========================================
   ANELLO {NOME} - {Descrizione} Theme
   ========================================== */
.{nome}-card {
    border-left: 3px solid rgba({colore}, 0.5);
}

.{nome}-card:hover {
    border-color: var(--accent-{nome});
}

.{nome}-card h2 {
    color: var(--accent-{nome});
}

/* Quartieri/Distretti - varianti colore */
.district-{nome1} { border-left: 3px solid rgba(..., 0.5); }
.district-{nome2} { border-left: 3px solid rgba(..., 0.5); }
/* ... uno per ogni quartiere/distretto */
```

---

## 🧭 CSS Paths Corretti per Profondità

**FONDAMENTALE:** Il path CSS deve corrispondere alla profondità del file.

| Livello | Path File | CSS Path | Esempio |
|---------|-----------|----------|---------|
| 2 | `anelli/file.html` | `../../css/style.css` | Landing anello |
| 4 | `distretti/{anello}/locations/file.html` | `../../../../css/style.css` | Location Bronzo |
| 5 | `distretti/{anello}/quartieri/{nome}/file.html` | `../../../../../css/style.css` | Quartiere Argento |
| 4 | `distretti/{anello}/{distretto}/file.html` | `../../../../css/style.css` | Distretto Bronzo |

**Formula:** Conta le barre `/` nel path dalla root `docs/` e aggiungi un `../` per ogni livello + 2 per raggiungere `css/`

---

## ✅ Checklist Creazione Anello

### Pre-Implementazione
- [ ] Leggere il file markdown sorgente completo
- [ ] Contare quartieri/distretti (solitamente 8)
- [ ] Identificare locations importanti (opzionale)
- [ ] Identificare organizzazioni principali (opzionale)
- [ ] Scegliere colori tema (primario + varianti per ogni quartiere)
- [ ] Scegliere emoji distintive per ogni quartiere (8 totali)
- [ ] Creare motti per ogni quartiere (se non presenti)

### Implementazione CSS
- [ ] Aggiungere variabili colore in `:root`
- [ ] Creare classe principale `.{nome}-card`
- [ ] Creare classi varianti per ogni quartiere (`.district-{nome}`)
- [ ] (Opzionale) Classi per locations e organizzazioni

### Implementazione HTML - Landing Page
- [ ] Aggiornare `docs/ambientazione/index.html` con carta nuovo anello
- [ ] Creare `anelli/anello-{nome}.html`
- [ ] Aggiungere sezione quartieri/distretti con emoji
- [ ] (Opzionale) Aggiungere sezione Luoghi Importanti
- [ ] (Opzionale) Aggiungere sezione Organizzazioni
- [ ] (Opzionale) Aggiungere sezione Vita e Cultura

### Implementazione HTML - Quartieri/Distretti
- [ ] Creare directory structure
- [ ] Per ogni quartiere/distretto creare 4 file:
  - [ ] `index.html` (panoramica + 3 card con emoji)
  - [ ] `npc.html` (3-5 PNG caratterizzati)
  - [ ] `hook.html` (3-5 hook con tabelle difficoltà)
  - [ ] `caratteristiche.html` (descrizione, luoghi, atmosfera, pericoli)
- [ ] Verificare CSS paths per ogni file
- [ ] Aggiungere pulsanti navigazione con **pulsante centrale** "Torna all'Anello"

### Implementazione HTML - Sezioni Opzionali
- [ ] (Opzionale) Creare `locations/*.html` (10-15 locations)
- [ ] (Opzionale) Creare `organizzazioni/*.html` + index
- [ ] (Opzionale) Creare `extra/*.html` (vita-quotidiana, eventi, tensioni)

### Verifica Finale
- [ ] Contare file: totale corrisponde al previsto?
- [ ] Testare tutti i pulsanti di navigazione
- [ ] Verificare che ogni index.html abbia il pulsante centrale "Torna all'Anello"
- [ ] Aprire 3-5 file random: CSS carica correttamente?
- [ ] Contenuto in italiano e formattato correttamente?
- [ ] Home icon funziona da ogni pagina?
- [ ] Emoji visualizzate correttamente?

---

## 💡 Tips & Best Practices

### Naming Conventions
- **Directory:** `kebab-case` (es. `arti-eteree`, `porto-celeste`)
- **CSS Classes:** `kebab-case` con prefisso tipo (es. `district-porto`, `location-teatro`)
- **File:** `kebab-case.html` (es. `galleria-artefatti.html`)

### Emoji per Quartieri/Distretti

Scegliere emoji che rappresentano **visivamente il tema principale**:

**Esempi Anello di Bronzo:**
- ⚓ Porto Celeste (porto/commercio)
- ⚒️ Fucine (artigianato/metallo)
- 🍲 Fornelli (cibo/cucina)
- 🎭 Lamenti (tragedia/povertà)
- 📚 Librai (sapere/libri)
- 🛍️ Botteghe (commercio)
- 🛡️ Guardia (ordine/legge)
- 🌙 Sussurri (segreti/notte)

**Esempi Anello d'Argento:**
- ⚗️ Alchimisti (scienza/magia)
- 🎨 Arti Eteree (arte/creatività)
- 💎 Collezionisti (ricchezza/rarità)
- 🌿 Giardini (natura/magia vita)
- 📖 Librai (sapere avanzato)
- 🏪 Mercato (commercio raffinato)
- 🎓 Scuole (educazione)
- 🧵 Tessitori (artigianato magico)

### Motti/Sottotitoli

Pattern comune per creare motti evocativi:
1. "Dove {soggetto} {verbo} {complemento}"
2. "{Nome} - {Descrizione Evocativa}"
3. "{Tema Principale} e {Tema Secondario}"

**Esempi:**
- "Dove la Cultura Diventa Magia"
- "Il Cuore del Commercio Raffinato"
- "Dove i Segreti Sono Merce Preziosa"
- "Ordine nell'Oceano del Caos"

### Contenuto NPC (npc.html)

**Elementi essenziali:**
- Nome completo
- Razza ed età
- Descrizione fisica (2-3 righe)
- Background/storia (1 paragrafo)
- Personalità e motivazioni
- (Opzionale) Segreto o hook personale

**Numero consigliato:** 3-5 NPC per quartiere

### Contenuto Hook (hook.html)

**Struttura hook:**
1. Titolo accattivante
2. Tipo (Investigazione/Combattimento/Sociale/etc.)
3. Descrizione situazione iniziale
4. Tabella difficoltà WFRP 4E (6-8 azioni)
5. Possibili sviluppi (3-4 scenari)

**Numero consigliato:** 3-5 hook per quartiere

### Tabelle Difficoltà WFRP 4E

Usare le difficoltà canoniche:
- **Facile** - Prove di routine
- **Media** - Sfide standard
- **Difficile** - Prove impegnative
- **Molto Difficile** - Imprese eccezionali
- **Ardua** - Quasi impossibile

---

## 🚀 Workflow Consigliato

1. **Preparazione** (30 min):
   - Leggere markdown sorgente
   - Contare sezioni e quartieri
   - Scegliere colori ed emoji
   - Creare lista motti

2. **CSS** (15 min):
   - Aggiungere variabili colore
   - Creare classi tema

3. **Landing Page** (20 min):
   - Creare `anelli/anello-{nome}.html`
   - Aggiungere tutte le sezioni con card

4. **Structure** (10 min):
   - Creare directory quartieri/distretti
   - Creare directory opzionali (locations, organizzazioni, extra)

5. **Bulk Creation - Quartieri** (automatico con Task agent):
   - Creare tutti i file quartieri (index, npc, hook, caratteristiche)
   - **IMPORTANTE:** Verificare pulsanti navigazione con pulsante centrale

6. **Bulk Creation - Opzionali** (automatico con Task agent):
   - Creare locations
   - Creare organizzazioni
   - Creare extra

7. **Verification** (20 min):
   - Controllare CSS paths
   - Testare tutti i link di navigazione
   - Verificare pulsante centrale "Torna all'Anello" presente ovunque

8. **Testing** (10 min):
   - Aprire sito localmente
   - Navigare tra le pagine
   - Verificare emoji e formattazione

**Tempo totale stimato:** ~2 ore per anello completo

---

## 📚 Riferimenti

**File Template da Consultare:**

- **Landing pages:**
  - `docs/ambientazione/anelli/anello-di-bronzo.html`
  - `docs/ambientazione/anelli/anello-d-argento.html`

- **Quartieri/Distretti (struttura piatta - Bronzo):**
  - `docs/ambientazione/distretti/anello-di-bronzo/porto-celeste/index.html`
  - `docs/ambientazione/distretti/anello-di-bronzo/porto-celeste/npc.html`
  - `docs/ambientazione/distretti/anello-di-bronzo/porto-celeste/hook.html`
  - `docs/ambientazione/distretti/anello-di-bronzo/porto-celeste/caratteristiche.html`

- **Quartieri (cartella quartieri - Argento):**
  - `docs/ambientazione/distretti/anello-d-argento/quartieri/alchimisti/index.html`
  - `docs/ambientazione/distretti/anello-d-argento/quartieri/alchimisti/npc.html`
  - `docs/ambientazione/distretti/anello-d-argento/quartieri/alchimisti/hook.html`
  - `docs/ambientazione/distretti/anello-d-argento/quartieri/alchimisti/caratteristiche.html`

- **Locations:**
  - `docs/ambientazione/distretti/anello-d-argento/locations/teatro-etereo.html`
  - `docs/ambientazione/distretti/anello-di-bronzo/locations/faro-di-azyr.html`

- **Organizzazioni:**
  - `docs/ambientazione/distretti/anello-di-bronzo/organizzazioni/gilda-mercanti.html`
  - `docs/ambientazione/distretti/anello-d-argento/organizzazioni/gilda-artisti.html`

- **Extra:**
  - `docs/ambientazione/distretti/anello-di-bronzo/extra/vita-quotidiana.html`
  - `docs/ambientazione/distretti/anello-di-bronzo/extra/eventi-ricorrenti.html`
  - `docs/ambientazione/distretti/anello-di-bronzo/extra/tensioni.html`

- **CSS:**
  - `docs/css/style.css` (cercare sezioni "ANELLO DI BRONZO" e "ANELLO D'ARGENTO")

**Prompt per Task Agent:**

Quando usi l'agente per creare file massivamente, fornisci:
- Path file sorgente markdown completo
- Nomi quartieri con emoji e motti
- Classi CSS da usare
- Lista completa file da creare
- Richiesta esplicita di includere pulsanti navigazione con **pulsante centrale "Torna all'Anello"**

---

*Aggiornato: 2025-01-08 | Pattern Unificato Standardizzato | Progetto Accademia Arcanis - Zephyra*
