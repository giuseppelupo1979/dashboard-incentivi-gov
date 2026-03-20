# 📊 Dashboard Incentivi.gov

Una web app interattiva **completamente autonoma** (un solo file HTML) per esplorare, filtrare e analizzare i bandi del dataset ufficiale [Incentivi.gov](https://www.incentivi.gov.it/) — con esportazione diretta in **PowerPoint**.

> **Nessuna installazione richiesta.** Basta aprire `dashboard.html` nel browser.

---

## ✨ Funzionalità

### 📂 Caricamento dati
- Carica il file `opendata-export.json` scaricato da Incentivi.gov tramite **drag & drop** o file picker
- Tutto viene elaborato **localmente nel browser** — nessun dato viene inviato a server esterni

### 🃏 Visualizzazione a card
- Griglia responsive: 3 colonne desktop → 2 tablet → 1 mobile
- Ogni card mostra i **KPI principali**: importo massimo, scadenza con colore semantico (🟢 attivo / 🟡 in scadenza / 🔴 scaduto), ente concedente, destinatari
- **Colore categoria** automatico basato su obiettivo/finalità (ecologia, digitale, innovazione, internazionalizzazione…)
- Clic su una card → pannello laterale con tutti i dettagli e il link istituzionale cliccabile

### 🔍 Ricerca e filtri
Barra di ricerca full-text + sidebar filtri con **10 dimensioni**:

| Filtro | Tipo |
|---|---|
| Solo bandi attivi | Checkbox — esclude tutti i bandi con scadenza passata |
| Scadenza indicata | Radio: Tutti / Con scadenza / Senza scadenza |
| Importo agevolazione | Slider doppio (range min/max) + input numerici |
| Tipologia soggetto | Multi-checkbox (Impresa, PA, Comune…) |
| Dimensione impresa | Multi-checkbox (Micro, Piccola, Media…) |
| Obiettivo / Finalità | Multi-checkbox con ricerca interna |
| Forma agevolazione | Multi-checkbox (Fondo perduto, Finanziamento…) |
| Settore attività | Multi-checkbox con ricerca interna |
| Regioni | Multi-checkbox con ricerca interna |
| Ambito territoriale | Multi-checkbox |

- I filtri attivi appaiono come **chip removibili** sopra la griglia
- Reset globale con un click
- Su mobile: pulsante "Filtri" che apre un pannello laterale

### 📊 Statistiche
Barra KPI in cima alla dashboard:
- Totale bandi caricati
- Bandi aperti (con percentuale sul totale)
- Bandi scaduti
- Stanziamento totale stimato

### 🖱️ Selezione multipla e Export PowerPoint
1. Clicca il **cerchio** in alto a destra di ogni bando per selezionarlo (evidenziato in viola con ✓)
2. Compare una **barra flottante** in basso con il conteggio delle selezioni
3. Clicca **"Esporta PPT"** → viene generato e scaricato automaticamente un file `.pptx`

#### Design di ogni slide (formato 16:9 — LAYOUT_WIDE)
```
┌──────────────── BARRA COLORATA CATEGORIA ───────────────────┐
│ COLONNA SINISTRA           │ COLONNA DESTRA                 │
│ (sfondo grigio chiaro)     │ (sfondo bianco)                │
│                            │                                │
│ [Badge categoria]          │ DESCRIZIONE                    │
│                            │ Testo completo del bando…      │
│ Titolo del bando           │                                │
│                            │ ─────────────────────────────  │
│ ENTE CONCEDENTE            │ COSTI AMMESSI                  │
│ Nome ente…                 │ Costo1 · Costo2 · …            │
│                            │                                │
│ ┌──────────┐ ┌──────────┐  │ DESTINATARI  │ FORMA AGEV.    │
│ │ € 500K   │ │ 15/12/24 │  │ Impresa      │ Fondo perduto  │
│ └──────────┘ └──────────┘  │                                │
│ REGIONI: Lombardia…        │ ▓ Dashboard Incentivi.gov ▓    │
│ 🔗 https://link.ufficiale  └────────────────────────────────┘
└────────────────────────────
```
- Colori KPI semantici: verde (attivo), ambra (≤30 gg), rosso (scaduto)
- Colori categoria coerenti con la dashboard
- Branding strip con data di generazione
- File nominato automaticamente: `Incentivi_YYYY-MM-DD_Nbandi.pptx`

---

## 🚀 Come si usa

```
1. Scarica  →  dashboard.html
2. Doppio clic per aprirlo nel browser
3. Carica opendata-export.json
4. Filtra, cerca, seleziona
5. Clicca "Esporta PPT" per scaricare la presentazione
```

### Download del dataset
Il file JSON si scarica da:
> **https://www.incentivi.gov.it/it/opendata**

---

## 🛠️ Dettagli tecnici

| Voce | Dettaglio |
|---|---|
| Tecnologia | HTML5 + CSS custom + Vanilla JS ES6 |
| Framework | **Nessuno** |
| Dipendenze esterne | **Nessuna** — tutto embedded nel file |
| Libreria PPT | [PptxGenJS 3.12.0](https://gitbookio.github.io/pptxgenjs/) — embedded inline |
| Dimensione file | ~533 KB (libreria PPT inclusa) |
| Compatibilità | Chrome, Firefox, Safari, Edge (versioni moderne) |
| Server richiesto | ❌ No — apre da `file://` |
| Connessione internet | ❌ No — completamente offline |
| Dati inviati a server | ❌ Mai — tutto locale |

---

## 📁 Struttura repository

```
dashboard.html    ← L'intera applicazione in un unico file
README.md         ← Questa documentazione
```

---

## 📋 Changelog

### v2.1
- Aggiunto filtro **"Scadenza indicata"**: filtra bandi con o senza data di chiusura specificata

### v2.0
- Selezione multipla bandi
- Export PowerPoint automatico (una slide per bando)
- PptxGenJS embedded inline — zero dipendenze esterne

### v1.0
- Dashboard con griglia card, filtri avanzati, ricerca full-text
- Pannello dettaglio laterale con link istituzionale

---

## 🗂️ Fonte dati

I dati provengono dal portale ufficiale italiano degli incentivi alle imprese:
- **Sito**: https://www.incentivi.gov.it/
- **Dataset**: opendata-export.json (aggiornato periodicamente dal MIMIT)
- **Licenza dati**: Open Data pubblici — Ministero delle Imprese e del Made in Italy

---

## 👤 Autore

**Giuseppe Lupo** — [@giuseppelupo1979](https://github.com/giuseppelupo1979)

---

## 📄 Licenza

MIT — libero utilizzo, modifica e distribuzione con attribuzione.
