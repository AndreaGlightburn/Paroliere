# Paroliere

PWA single-HTML per allenare la mente con un gioco di parole stile Ghigliottina de *L'Eredità*.

**Live demo**: https://andreaglightburn.github.io/Paroliere/ (dopo attivazione Pages)

## Modalità di gioco

- **Classica** — 5 indizi, scrivi la parola che li unisce. Montepremi 100.000 € che si dimezza ad ogni errore o indizio nascosto (jolly "Dimezza").
- **Scelta multipla** — 5 indizi + opzioni fra cui scegliere (4/6/8 configurabili). Punteggio 100, −20 ad ogni sbaglio.
- **A trattini** — parola nascosta come `_ _ _ _ _`. A ogni errore una lettera appare in posizione casuale, ma il punteggio dimezza.

## Difficoltà configurabile (home)

- **Lunghezza parola**: Facile (3-5 lettere) · Media (6-8) · Difficile (9+) · Qualsiasi
- **Tentativi** (modalità A trattini): 3 · 5 · 7 · Auto (70% della lunghezza)
- **Opzioni** (modalità Scelta multipla): 4 · 6 · 8

Le preferenze restano salvate in localStorage.

## Caratteristiche

- 📱 Mobile-first, installabile come PWA (icona "Aggiungi a home")
- 🌙 Dark mode automatico in base al tema di sistema
- 💾 Funziona completamente offline (service worker inline)
- 📊 Statistiche personali in localStorage (partite, vittorie, record per modalità)
- ➕ Enigmi personalizzati caricabili da file JSON o paste
- 🤖 Prompt pronto per Claude/ChatGPT/Gemini per generare nuovi enigmi
- 🎯 65 enigmi italiani pre-costruiti pescati a caso

## Deploy

È un singolo file `index.html` autonomo: funziona ovunque, nessuna build.

### GitHub Pages

1. Repository **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)`
4. **Save**

Dopo 1-2 minuti è live su https://andreaglightburn.github.io/Paroliere/

(Nota: GitHub Pages gratuito richiede che il repo sia **public**.)

### Hosting proprio (Aruba, ecc.)

Copia `index.html` nella webroot. Niente da installare.

## Generare nuovi enigmi con AI

Dalla schermata **Impostazioni → Genera con AI** copi un prompt già pronto. Lo incolli in Claude, ChatGPT, Gemini o altra AI — ti restituisce un array JSON di 30 enigmi che carichi con il pulsante **📁 Carica file JSON**.

Il prompt è progettato per produrre output nel formato esatto, senza blocchi markdown, con le regole del gioco:
- Target in maiuscolo, singola parola
- 5 indizi in maiuscolo, ciascuno una sola parola
- Collocazioni italiane comuni e riconoscibili
- No ripetizioni dei target già presenti
- No nomi propri o marchi

## Formato enigmi

```json
[
  {
    "target": "CASA",
    "clues": ["TETTO", "PORTA", "MURO", "FAMIGLIA", "DOLCE"]
  }
]
```

Il pulsante **Esporta tutti** scarica un JSON con base + personalizzati, utile per condividere raccolte tra più dispositivi o volontari.

## Roadmap

- [ ] Backend AI opzionale (iz2oii.eu) per generazione procedurale on-demand
- [ ] Modalità "Sfida giornaliera" (stesso enigma per tutti nel giorno, seed data)
- [ ] Varianti: catena di parole, anagrammi tematici, memoria breve
- [ ] Database collocazioni italiane precalcolate (corpus Paisà / itWaC)

## Licenza

Uso libero.
