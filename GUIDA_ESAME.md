# GUIDA RAPIDA — ESAME 15 GIUGNO
## Struttura del progetto

```
src/
 ├── data.js       ← DATI e LOGICA (tocca questo per primo)
 ├── App.jsx       ← LAYOUT + PAGINE (tocca etichette e testi)
 ├── index.css     ← STILI (tocca solo se vuoi cambiare colori)
 └── main.jsx      ← non toccare
```

---

## ✅ CHECKLIST ESAME — cosa cambiare e dove

### 1. `data.js` — adatta il dominio

| Riga | Cosa fare |
|------|-----------|
| `TIPI = [...]` | Sostituisci con le tue categorie (es. `["Libro", "DVD", "Rivista"]`) |
| `STATI = [...]` | Sostituisci con i tuoi stati (es. `["Disponibile", "Prestato"]`) |
| `elementi_iniziali` | Cambia i nomi e i valori (campo1, campo2 → es. capienza, prezzo) |
| `transazioni_iniziali` | Aggiorna con i tuoi dati di esempio |
| `calcolaQuantita` | Lasciala così oppure cambia la formula se non è oraria |

### 2. `App.jsx` — rinomina le etichette

Cerca i commenti `✏️ ESAME:` nel file — sono ~15 punti precisi.

**Più importanti:**
- `const voci = [...]` → nomi del menu sidebar (es. "Libri", "Prestiti", "Report")
- `<span className="logo-acc">` → prima parte del brand
- `<span className="logo-brand">` → seconda parte del brand
- `<span className="badge-data">` → **metti la data del giorno come stringa fissa** (es. `"15 giugno 2025"`)
- Titoli `<h2 className="titolo-pagina">` in ogni pagina
- Label delle colonne tabella in `PaginaReport`
- Label "Campo 1" / "Campo 2" nei form → rinomina con i nomi reali

**Nota:** se aggiungi/rimuovi campi in `elementi_iniziali` ricordati di aggiornare anche il form in `PaginaElementi` e le celle della tabella in `PaginaReport`.

### 3. `index.css` — colori (opzionale)

Se vuoi aggiungere un tocco di colore basta cambiare le variabili in `:root`:
```css
--acc: #2563eb;        /* colore principale (bottoni, chip attivi) */
--tipo-a: #2563eb;     /* badge tipo A */
--tipo-b: #16a34a;     /* badge tipo B */
--tipo-c: #d97706;     /* badge tipo C */
--stato-ok: #16a34a;   /* stato positivo */
--stato-busy: #dc2626; /* stato occupato */
```

### 4. `index.html` — titolo scheda browser
```html
<title>Il mio progetto</title>
```

---

## ⚡ AVVIO RAPIDO

```bash
npm install
npm run dev
```

Apri `http://localhost:5173`

---

## 🗂 Flusso dati (come si collega tutto)

```
data.js  →  useDati()  →  App.jsx  →  PaginaElementi
                                    →  PaginaTransazioni
                                    →  PaginaReport
```

- `useDati()` restituisce: `elementi`, `transazioni`, e le 3 funzioni
- Le pagine ricevono tutto via props (`{...dati}`)
- I grafici leggono direttamente da `transazioni` e `elementi`

---

## ❌ NON TOCCARE

- `main.jsx`
- `vite.config.js`
- `package.json`
- La logica di `useEffect` nei grafici (funziona già)
- La funzione `CampoForm` in fondo ad App.jsx
