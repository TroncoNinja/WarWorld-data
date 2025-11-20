# Struttura dati armi

Descrive il formato del file JSON che elenca le categorie di armi e le loro statistiche base.

## Schema concettuale

```
categoria: [
  {
    "nome": string,
    "stat_hand": number,      // combattimento ravvicinato
    "stat_short": number,     // gittata corta
    "stat_medium": number,    // gittata media
    "stat_long": number,      // gittata lunga
    "stat_ferite": number     // danno / ferite inflitte
  }
]
```

## Regole
- Tutte le statistiche sono interi >= 0.
- Le categorie devono avere un nome univoco.
- I campi sono obbligatori.

## Esempio

```JSON
{
  "categoria": [
    {
      "nome": "Fucile d'assalto",
      "stat_hand": 2,
      "stat_short": 6,
      "stat_medium": 5,
      "stat_long": 3,
      "stat_ferite": 4
    },
    {
      "nome": "Pistola",
      "stat_hand": 3,
      "stat_short": 4,
      "stat_medium": 1,
      "stat_long": 0,
      "stat_ferite": 2
    }
  ]
}
```