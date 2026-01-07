# Struttura dati plate carrier

Descrive il formato del file JSON che elenca i plate carrier e i loro effetti meccanici.

## Schema concettuale

```
[
  {
    "nome": string,
    "descrizione": array of strings, // descrizione riga per riga
    "mod": object                   // mappa di modificatori numerici
  }
]
```

## Regole
- Tutti i campi principali (nome, descrizione, mod) sono obbligatori.
- Ogni stringa in "descrizione" rappresenta una riga; l'array non deve essere vuoto.
- Le chiavi dentro "mod" descrivono i valori base o i vincoli applicati e accettano valori numerici (interi o decimali), generalmente >= 0.
- Le chiavi di "mod" devono essere univoche all'interno dello stesso plate carrier; nomi chiave coerenti con l'effetto (es. ca_base, forced_recovery).

## Esempio

```JSON
[
  {
    "nome": "Plate Carrier - Reattivo",
    "descrizione": [
      "CA base: 1",
      "cura automaticamente la prima ferita ogni {da bilanciare}"
    ],
    "mod": {"ca_base": 1}
  },
  {
    "nome": "Plate Carrier - Rinforzato",
    "descrizione": [
      "CA base: 3",
      "dopo 4 metri totali di spostamento durante la fase di ingaggio, l'operatore deve usare l'azione di Recupero"
    ],
    "mod": {"ca_base": 3, "forced_recovery": 4}
  }
]
```
