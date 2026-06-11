# Momento di preghiera con i maturandi — Notte prima degli esami

Pagina web statica e auto-contenuta per il momento di preghiera con i maturandi alla
vigilia dell'Esame di Stato (17 giugno 2026). Tutto il sito è in un unico file,
`index.html`, con CSS e JavaScript inline: nessuna build, nessuna dipendenza esterna.

## Anteprima locale

Apri direttamente `index.html` nel browser, oppure avvia un server locale dalla
cartella del progetto:

```bash
python3 -m http.server
```

e visita `http://localhost:8000`.

## Deploy su GitHub Pages

1. Fai il push del repository su GitHub (branch `main`).
2. Su GitHub vai in **Settings → Pages**.
3. In **Build and deployment**, scegli **Deploy from a branch**, seleziona il branch
   `main` e la cartella `/ (root)`.
4. Salva: dopo qualche minuto il sito sarà disponibile su
   `https://<username>.github.io/notteprimaesami/`.

### Dominio personalizzato (opzionale)

Per usare un dominio personalizzato al posto di `username.github.io/notteprimaesami`,
aggiungi un file `CNAME` nella root del repository contenente il dominio (es.
`preghiera-maturandi.it`) e configura i record DNS come indicato nella
[documentazione di GitHub Pages](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site).
Per un normale indirizzo `username.github.io/notteprimaesami` non serve nulla di
più di quanto già presente.

### Aggiornare i meta Open Graph

In `index.html`, il tag `<meta property="og:url" content="https://USERNAME.github.io/notteprimaesami/">`
contiene un segnaposto: sostituiscilo con l'URL reale del sito una volta pubblicato,
così le anteprime di condivisione (es. su WhatsApp, social) puntano all'indirizzo corretto.

## Funzionalità

- **Tema chiaro/scuro**: segue di default le preferenze di sistema
  (`prefers-color-scheme`); il pulsante "Tema" permette di forzare una scelta,
  salvata in `localStorage`.
- **Dimensione testo regolabile**: i pulsanti `A−` / `A` / `A+` cambiano la
  dimensione del testo, salvata in `localStorage`.
- **Indice** in cima alla pagina per saltare direttamente a una delle quattro parti.
- **Note a piè di pagina** con le fonti delle citazioni di Papa Leone XIV.

## Checklist di verifica finale

- [ ] Tutte e quattro le sezioni sono presenti e il testo corrisponde verbatim a
      `Momento_di_preghiera_maturandi_2026.docx` (Introduzione, Preghiera dei
      maturandi con le 7 invocazioni, Preghiera a San Giuseppe da Copertino,
      Benedizione finale).
- [ ] Le risposte `Tutti: Ascoltaci, Signore` e i cue `Preghiamo.` sono evidenziati
      correttamente; gli `Amen` sono nel colore di accento.
- [ ] Il toggle del tema funziona e la preferenza resta dopo un refresh della pagina.
- [ ] I pulsanti `A−` / `A` / `A+` cambiano la dimensione del testo e la preferenza
      resta dopo un refresh.
- [ ] La pagina è leggibile su schermo mobile (~375px di larghezza) e su desktop.
- [ ] Navigazione completa da tastiera (skip-link, indice, pulsanti, link alle note)
      con focus sempre visibile.
- [ ] `og:url` aggiornato con l'indirizzo reale del sito dopo il deploy.
