# Struttura dati addestramento

Descrive il formato del file JSON che elenca i percorsi di addestramento e i bonus associati.

## Schema concettuale

```
[
  {
    "nome": string,
    "descrizione": array of strings, // descrizione riga per riga
    "mod": object                   // mappa di bonus numerici
  }
]
```

## Regole
- Tutti i campi principali (nome, descrizione, mod) sono obbligatori.
- Ogni stringa in "descrizione" rappresenta una riga; l'array non deve essere vuoto.
- Le chiavi dentro "mod" descrivono il bonus conferito e accettano valori numerici (interi o decimali), generalmente >= 0.
- Le chiavi di "mod" devono essere univoche all'interno della stessa voce; usare nomi coerenti con l'effetto (es. short_add, medium_add, long_add).

## Esempio

```JSON
[
    {
        "nome": "Fanteria",
        "descrizione": [
            "sei il soldato d'assalto perfetto, eccelli nei combattimenti ravvicinati.",
            "Bonus: +1 short"
        ],
        "mod": {"short_add": 1}
    },
    {
        "nome": "Tiratore",
        "descrizione": [
            "un addestramento che comprende le armi a lunga gittata ti ha reso letale per chiunque incroci la tua ottica.",
            "Bonus: +1 long"
        ],
        "mod": {"long_add": 1}
    }
]
```
