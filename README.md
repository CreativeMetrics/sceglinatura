# Report SEO · sceglinatura.com

Report di posizionamento organico basato sui dati SEOZoom, con sistema di snapshot storici per i confronti temporali.

## Struttura del repository

```
.
├── index.html                    ← il report (pagina principale)
├── data/
│   ├── logo.png                  ← logo del brand
│   ├── snapshots_index.json      ← elenco degli snapshot disponibili
│   ├── snapshot_YYYY-MM-DD.json  ← uno snapshot per data
│   └── recommendations.json      ← raccomandazioni testuali (editabili a mano)
└── README.md
```

## Come aggiornare i dati (snapshot)

1. Scarica i nuovi export da SEOZoom (XLSX)
2. Apri il report online: `https://[username].github.io/sceglinatura-seo/`
3. Clicca **"+ Aggiorna dati"** in alto a destra
4. Trascina gli 8 file XLSX nel pannello
5. Conferma la data del rilievo (preimpostata a oggi)
6. Clicca **"Genera snapshot"** → il browser scarica `snapshot_AAAA-MM-GG.json`
7. Carica quel file su GitHub nella cartella `data/`
8. Aggiorna anche `snapshots_index.json` aggiungendo una riga (il report mostra il testo esatto da incollare)
9. Ricarica il report (Ctrl+F5)

## Come modificare le raccomandazioni manualmente

Le raccomandazioni in fondo al report NON si aggiornano automaticamente coi nuovi dati: sono commenti strategici che vanno rivisti periodicamente.

### Modifica diretta su GitHub

1. Vai sul repository, apri `data/recommendations.json`
2. Clicca l'icona della matita (Edit) in alto a destra
3. Modifica il testo (vedi struttura sotto)
4. Aggiorna il campo `updated_at` con la data di oggi
5. Scendi in fondo e clicca Commit changes
6. Ricarica il report (Ctrl+F5)

### Struttura di `recommendations.json`

```json
{
  "title": "Titolo della sezione con <span class=\"accent\">parole in verde</span>",
  "intro": "Paragrafo introduttivo opzionale",
  "updated_at": "2026-05-20",
  "items": [
    {
      "priority": "high",
      "title": "Titolo raccomandazione",
      "body": "Testo. Ammessi tag HTML semplici: <code>...</code>, <strong>...</strong>"
    }
  ]
}
```

Valori ammessi per `priority`: `"high"` (rosso), `"med"` (oro), `"low"` (verde tenue).

## Note tecniche

- Il report funziona interamente lato client (JavaScript nel browser)
- Nessun dato esce dal tuo browser durante l'elaborazione degli XLSX
- Sezioni dinamiche (auto-aggiornate): Sintesi, KPI, grafici, tabelle, Insight, Confronti
- Sezione statica (modifica manuale): Raccomandazioni
