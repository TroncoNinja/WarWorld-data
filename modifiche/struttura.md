# Struttura dati modifiche

Descrive il formato del file JSON che elenca le modifiche possibili e i loro effetti meccanici.

## Schema concettuale

```
modifiche: [
  {
    "nome": string,
    "descrizione": array of strings, // descrizione riga per riga
    "mod": object                   // mappa di modificatori numerici o booleani
  }
]
```

## Regole
- Tutti i campi principali (nome, descrizione, mod) sono obbligatori.
- Ogni stringa in "descrizione" rappresenta una riga; l'array non deve essere vuoto.
- Le chiavi dentro "mod" descrivono l'effetto applicato e accettano valori booleani (true/false) o numerici (interi o decimali >= 0).
- Le chiavi di "mod" devono essere univoche all'interno della stessa modifica; nomi chiave coerenti con l'effetto che descrivono.

## Esempio

```JSON
{
  "modifiche": [
    {
      "nome": "Meta umano - Pesante",
      "descrizione": [
        "il tuo DNA è stato alternato con elementi di animali di grande prestanza fisica (es. gorilla, rinoceronte, …).",
        "Puoi equipaggiare un’arma Media nello slot per arma secondaria"
      ],
      "mod": {"heavy_weapon_slot": true}
    },
    {
      "nome": "Meta umano - Sensoriale",
      "descrizione": [
        "il tuo DNA è stato alternato con elementi di animali di grande capacità sensoriale (es. pipistrelli, delfini, …).",
        "Il cerchio della tua Visione aumenta il suo raggio a 3 metri."
      ],
      "mod": {"vision_radius": 3}
    }
  ]
}
```
