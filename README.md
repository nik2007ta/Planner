# La mia settimana

Planner settimanale mobile (PWA): lezioni, dieta, palestra, faccende domestiche, trading, altro — tutto in un unico posto, con una tabella cronologica che raccoglie ogni voce della giornata.

## Struttura del progetto

```
index.html          → l'app
manifest.json        → identità della PWA (nome, icona, colori)
service-worker.js    → cache offline
icons/                → icone in tutte le dimensioni richieste
```

## Pubblicare su GitHub Pages

1. Crea un nuovo repository su GitHub (es. `settimana-planner`), pubblico.
2. Carica dentro tutti i file di questa cartella **mantenendo la struttura** (in particolare la cartella `icons/` va copiata così com'è, non svuotata).
   - Da web: "Add file" → "Upload files", trascina tutto (compresa la cartella `icons`).
   - Da terminale:
     ```
     git init
     git add .
     git commit -m "Prima versione del planner"
     git branch -M main
     git remote add origin https://github.com/TUO-USERNAME/settimana-planner.git
     git push -u origin main
     ```
3. Nel repository vai su **Settings → Pages**.
4. Sotto "Build and deployment", scegli **Deploy from a branch**, branch `main`, cartella `/ (root)`. Salva.
5. Dopo un minuto GitHub mostra l'indirizzo pubblico, del tipo:
   `https://TUO-USERNAME.github.io/settimana-planner/`
   Apri quel link: è la tua app, live.

## Installarla sul telefono (icona in home screen)

**Android (Chrome):** apri il link, tocca i tre puntini in alto a destra → "Installa app" (o "Aggiungi a schermata Home"). Comparirà con la sua icona come un'app normale, funziona anche offline dopo la prima apertura.

**iPhone (Safari):** apri il link, tocca l'icona di condivisione (il quadrato con la freccia) → "Aggiungi alla schermata Home". Su iOS *deve* essere Safari, non funziona da Chrome.

## Aggiornare l'app in futuro

Basta modificare `index.html` (o gli altri file) e rifare il push su GitHub — la pagina pubblicata si aggiorna da sola. Il service worker tiene una cache locale, quindi su un telefono che l'ha già installata a volte serve chiuderla del tutto e riaprirla (o attendere qualche secondo in più) perché la versione nuova sostituisca quella in cache.

## Nota sui dati

I dati del planner sono salvati localmente in modo persistente tramite l'archiviazione integrata dell'app: restano lì quando la richiudi o la riapri, ma sono legati a quel dispositivo/browser — non si sincronizzano automaticamente tra telefono e computer.
