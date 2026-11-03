# Paroliere · Ghigliottina Mente

PWA single-HTML per allenare la mente con un gioco di parole stile Ghigliottina de *L'Eredità*.

**Live demo**: https://andreaglightburn.github.io/Paroliere/

## Modalità di gioco

- **Classica** — 5 indizi, scrivi la parola che li unisce. Montepremi 100.000 € che si dimezza ad ogni errore o indizio nascosto (jolly "Dimezza").
- **Scelta multipla** — 5 indizi + 6 opzioni. 100 punti, −20 ad ogni sbaglio, max 3 errori.
- **A trattini** — parola nascosta come `_ _ _ _ _`. A ogni errore una lettera appare in posizione casuale, ma il punteggio dimezza.

## Caratteristiche

- 📱 Mobile-first, installabile come PWA (icona "Aggiungi a home")
- 🌙 Dark mode automatico in base al tema di sistema
- 💾 Funziona completamente offline (service worker inline)
- 📊 Statistiche personali in localStorage (partite, vittorie, record per modalità)
- ➕ Enigmi personalizzati caricabili come JSON
- 🎯 65 enigmi italiani pre-costruiti pescati a caso

## Deploy

È un singolo file `index.html` autonomo: funziona ovunque, nessuna build.

### GitHub Pages

1. Repository **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)`
4. **Save**

Dopo 1-2 minuti è live su https://andreaglightburn.github.io/Paroliere/

### Hosting proprio (Aruba, ecc.)

Copia `index.html` nella webroot. Niente da installare.

## Formato enigmi personalizzati

Da **Impostazioni → Enigmi personalizzati**, incolla un array JSON:

```json
[
  {
    "target": "CASA",
    "clues": ["TETTO", "PORTA", "MURO", "FAMIGLIA", "DOLCE"]
  }
]
```

Regole:
- `target`: la parola da indovinare (maiuscola, senza spazi vinci anche con minuscolo o con accenti diversi)
- `clues`: esattamente 5 indizi, ciascuno collegabile al target tramite una collocazione, un modo di dire o un composto comune in italiano

Il pulsante **Esporta tutti** scarica un JSON con base + personalizzati, utile per condividere raccolte tra più dispositivi o utenti.

## Roadmap

- [ ] Backend AI opzionale (iz2oii.eu) per generazione procedurale di enigmi inediti
- [ ] Modalità "Sfida giornaliera" (stesso enigma per tutti nel giorno, basato su seed data)
- [ ] Varianti: catena di parole, anagrammi tematici, memoria breve
- [ ] Database collocazioni italiane precalcolate (corpus Paisà / itWaC)

## Licenza

Uso libero.
