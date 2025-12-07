# Struttura dati armi

Descrive il formato del file JSON che elenca i tipi di gadget e i le loro caratteristiche.

## Schema concettuale

```
gadget: [
  {
    "nome": string,
    "descrizione": array of strings,      // descrizione riga per riga
  }
]
```

## Regole
- ogni stringa in "descrizione" rappresenta una riga.
- I campi sono obbligatori.

## Esempio

```JSON
{
  "gadget": [
    {
        "nome": "Scudo balistico",
        "descrizione": [
            "Lo scudo balistico va a sostituire l'arma nello slot principale.",
            "Fornisce una copertura aggiuntiva contro i danni da proiettile",
            "Quando equipaggiato fornisce mezza copertura per i colpi che arrivano frontalmente all'operatore"
        ]
    }
  ]
}
```