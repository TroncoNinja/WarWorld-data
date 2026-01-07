# WarWorld — Database TTRPG

Archivio dati per il gioco da tavolo "WarWorld": armi, gadget, veicoli e altre risorse in formato JSON. Scopo: rendere i contenuti riutilizzabili da master, giocatori e tool di supporto.


## Struttura delle cartelle

Il database è organizzato in macro-categorie (es: `equipaggiamento/`, `addestramento/`, `modifiche/`, `veicoli/`). Alcune macro-categorie, come `equipaggiamento/`, contengono a loro volta micro-categorie (sottocartelle) che rappresentano tipologie specifiche di oggetti:

- `equipaggiamento/armi/` — Armi suddivise per categoria (es: fucili_assalto, pistole, shotgun, ecc.). Ogni categoria è una chiave del file JSON che contiene un array di oggetti arma con statistiche per distanza (`hand`, `short`, `medium`, `long`).
- `equipaggiamento/gadget/` — Gadget speciali e strumenti di supporto. Ogni oggetto ha un nome e una descrizione (array di stringhe).
- `equipaggiamento/plate_carrier/` — Plate carrier e protezioni: ogni oggetto ha nome, descrizione (array di stringhe) e modificatori numerici (oggetto `mod`).

Altre macro-categorie:
- `modifiche/` — Modifiche genetiche, fisiche o tecnologiche applicabili ai personaggi. Ogni oggetto ha nome, descrizione (array di stringhe) e modificatori (oggetto `mod`, numerici o booleani).
- `addestramento/` — Percorsi di addestramento e bonus associati. Ogni oggetto ha nome, descrizione (array di stringhe) e bonus (oggetto `mod`).
- `veicoli/` — Veicoli e mezzi di trasporto. (Struttura da definire o documentata nel relativo `struttura.md` se presente.)

Altre cartelle: seguono formati simili, sempre documentati dal relativo `struttura.md`.

Ogni sottocartella include:
- `struttura.md`: descrive la struttura dati usata nei file JSON della cartella
- Un file `nomecartella.json` contenente i dati veri e propri

Per dettagli sulla struttura di ciascun file, consultare il relativo `struttura.md`.
