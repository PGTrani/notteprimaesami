Ottima idea: un brief in markdown è il modo migliore per passare il lavoro a una sessione di Claude Code. Te lo preparo con contesto, testo integrale verbatim, regole di formattazione e requisiti tecnici per GitHub Pages.Ecco il brief in markdown, pronto da passare a Claude Code. È strutturato in sette parti:

1. **Contesto** — cos'è, per chi, tono richiesto (pubblico giovane, molti non praticanti) e scopo del sito.
2. **Requisiti tecnici** — sito statico per GitHub Pages, `index.html` auto-contenuto, mobile-first, accessibilità WCAG AA, dark mode, meta Open Graph per l'anteprima quando si condivide il link. Ho specificato che su un sito vero `localStorage` è consentito (utile per ricordare tema e dimensione testo).
3. **Direzione grafica** — palette (accento bordeaux `#7B2D26`, sfondo avorio, versione scura), tipografia serif per le preghiere + sans per l'interfaccia, leggibilità ampia.
4. **Regole di formattazione** — come rendere ogni elemento: etichette delle voci (Celebrante / Maturando N), la risposta `Tutti: Ascoltaci, Signore` evidenziata, il cue `Preghiamo.` in grassetto, le orazioni a versi con gli a-capo conservati, le citazioni del Papa tra virgolette, gli `Amen` in accento.
5. **Testo integrale verbatim** — tutte e quattro le sezioni, già con la punteggiatura corretta e i "Preghiamo." al posto giusto, così Claude Code deve solo impaginarlo senza riscrivere nulla.
6. **Fonti delle citazioni** — i tre interventi di Papa Leone XIV con data, per un'eventuale nota a piè pagina.
7. **Output atteso** — file da produrre, README per il deploy e checklist di verifica finale.

Un paio di accorgimenti quando avvii la sessione di Claude Code: trascina o incolla questo file come primo messaggio e chiedi esplicitamente «realizza il sito secondo questo brief», così lo userà come specifica. Se vuoi un dominio personalizzato su GitHub Pages servirà anche un file `CNAME`, ma per un normale indirizzo `username.github.io/repo` non serve nulla di più di quanto già indicato.