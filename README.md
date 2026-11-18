# Machina Stochastica

![Version](https://img.shields.io/badge/version-1.14-8c632e?style=flat-square)
![License](https://img.shields.io/badge/license-AGPL--3.0-2c4031?style=flat-square)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Dependencies](https://img.shields.io/badge/dependencies-none-4a3520?style=flat-square)

**Calcolatore Balistico & Probabilistico per Giochi di Ruolo** — *Officina degli Enigmi · Machina N. 003 (Brevetto 1894)*.

Machina Stochastica e una web application single-file a tema steampunk progettata per simulare il lancio di dadi poliedrici, tiri percentuali e lanci della moneta attraverso manometri analogici animati, tamburi meccanici per i modificatori ed effetti sonori sincronizzati.

[Puoi giocarci qui](https://tagtthespellcaster.github.io/Machina-Stochastica/)

---

## Caratteristiche principali

- **Banchi di dadi poliedrici (`d4`, `d6`, `d8`, `d10`, `d12`)**:
  - Dieci manometri indipendenti per ciascuna tipologia di dado.
  - Selettore rotante **ON / OFF** per riga: in modalita **ON** attiva o disattiva i dadi in cascata dal primo fino a quello selezionato; in modalita **OFF** consente la selezione individuale di ogni singolo dado.
  - Tamburo cilindrico meccanico a due cifre (`00`–`99`) con commutatore di segno (`+` / `-`) comandabile tramite rotella del mouse o trascinamento verticale (pointer drag).
  - Indicatore digitale di subtotale per singola riga.

- **Sezione `2d20` — Tiro Critico**:
  - Selettore rotante a tre posizioni: **S** (Svantaggio: trattiene il valore minore), **N** (Normale: somma i dadi attivi) e **V** (Vantaggio: trattiene il valore maggiore).
  - Evidenziazione automatica del quadrante selezionato dal calcolo.
  - Tamburo modificatore dedicato con segno (`+/-`) e lettura diretta del risultato.

- **Sezione `d100` (Percentuale)**:
  - Doppio manometro analogico per **Decine** e **Unita** con lettura combinata da `01%` a `100%`.

- **Esclusione mutua dei gruppi di tiro**:
  - L'attivazione di uno qualsiasi tra i banchi standard (`d4`–`d12`), `2d20` o `d100` disattiva automaticamente gli altri gruppi, garantendo coerenza nel calcolo.

- **Moneta Testa o Croce**:
  - Simulazione fisica con animazione 3D (`CSS preserve-3d`) e lettura testuale dell'esito (`TESTA` / `CROCE`).

- **Valvola Generale (Vapore / Lancio) e Totalizzatore**:
  - Azionabile tramite clic o pressione dei tasti `Spazio` / `Invio`.
  - Sequenza audiovisiva sincronizzata: chiusura meccanica, ricalcolo balistico e sfiato del vapore.
  - Totalizzatore finale composto da tre manometri analogici (**Centinaia**, **Decine**, **Unita**) affiancato dal display numerico a tre cifre (`000`–`999`).

- **Layout adattivo**:
  - Adattamento automatico su desktop ad alta risoluzione (vista completa a schermo intero) e su schermi portatili con altezza ridotta (`max-height: 850px`), dove i manometri vengono ingranditi e la plancia inferiore diventa raggiungibile tramite scorrimento.

---

## Struttura del progetto e asset richiesti

L'applicazione e contenuta in un unico file HTML (`index.html`) privo di dipendenze esterne o framework, ma richiede la presenza nella stessa directory dei seguenti asset grafici e sonori:

### Asset grafici
- **Interruttori**: `horizon.png`, `horizoff.png`, `verton.png`, `vertoff.png`
- **Modificatori e tamburi**: `plus.png`, `minus.png`, `left.png`, `right.png`, `00.png` – `09.png` (con fallback automatico su `.jpg`)
- **Moneta**: `head.png`, `tails.png`

### Asset audio
- `clank.mp3`
- `steam-hissing.mp3`
- `breaker-switch.mp3`
- `button-press.mp3`
- `coin.mp3`

---

## Installazione e utilizzo

1. Clona o scarica il repository locale mantenendo il file HTML nella stessa cartella degli asset `.png` e `.mp3`.
2. Apri il file HTML direttamente in un browser moderno (Chrome, Firefox, Safari, Edge) oppure servilo tramite un qualsiasi server HTTP statico:

```bash
python3 -m http.server 8080
```

3. Seleziona i dadi desiderati tramite gli interruttori orizzontali, imposta gli eventuali modificatori sui tamburi rotanti e aziona l'interruttore **Vapore** per eseguire il lancio.

---

## Licenza

Questo progetto e distribuito sotto i termini della **GNU Affero General Public License v3.0 (AGPL-3.0)**. Consulta il file `LICENSE` nel repository o il testo ufficiale su [gnu.org/licenses/agpl-3.0](https://www.gnu.org/licenses/agpl-3.0.html) per i dettagli completi.
