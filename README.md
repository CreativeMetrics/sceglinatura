# Report SEO · sceglinatura.com

Report di posizionamento organico basato sui dati SEOZoom, con sistema di snapshot storici per i confronti temporali.

## Struttura del repository

```
.
├── index.html                    ← il report (pagina principale)
├── data/
│   ├── logo.png                  ← logo del brand
│   ├── snapshots_index.json      ← elenco degli snapshot disponibili
│   └── snapshot_YYYY-MM-DD.json  ← uno snapshot per data
└── README.md
```

## Come aggiornare i dati

1. Scarica i nuovi export da SEOZoom (XLSX o CSV)
2. Apri il report online: vai su `https://[tuo-username].github.io/sceglinatura-seo/`
3. Clicca su **"Aggiorna dati"** in alto a destra
4. Trascina gli 8 file XLSX nel pannello
5. Conferma la data del rilievo (preimpostata a oggi)
6. Clicca **"Genera snapshot"** → scarica un file `snapshot_AAAA-MM-GG.json`
7. Carica quel file su GitHub:
   - Vai nella cartella `data/` del repository
   - Clicca **Add file → Upload files**
   - Trascina il file JSON appena scaricato
   - Aggiorna anche `snapshots_index.json` aggiungendo una riga per il nuovo snapshot
   - Conferma con **Commit changes**
8. Ricarica il report nel browser → vedrai i nuovi dati e i confronti aggiornati

## Snapshot disponibili

Vedere `data/snapshots_index.json`

## Note tecniche

- Il report funziona interamente lato client (JavaScript nel browser)
- Nessun dato esce dal tuo browser durante l'elaborazione degli XLSX
- Gli snapshot storici vengono caricati da GitHub Pages via fetch HTTPS
