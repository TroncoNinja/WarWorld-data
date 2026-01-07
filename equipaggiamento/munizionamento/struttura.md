# Struttura dati munizionamento

Descrive il formato del file JSON che elenca le munizioni disponibili per ciascuna categoria di arma e i loro effetti meccanici.

## Schema concettuale

```
{
  "categoria": [
    {
      "nome": string,         // nome della munizione
      "ferite": number,       // danno/ferite inflitte
      "mod": object           // modificatori geometrici (opzionale)
    }
  ],
  ...altre categorie
}
```

## Regole
- Tutte le statistiche sono numeri interi >= 0.
- Le categorie (es: "fucili_assalto", "shotgun", ecc.) sono chiavi univoche del file JSON.
- Ogni munizione deve avere i campi "nome" e "ferite" obbligatori.
- Il campo "mod" è opzionale e contiene modificatori (es: confirmation_dice, hit_dice).
- I modificatori di "mod" non si applicano all'arma, ma rispettivamente al dado di tiro (hit_dice) o al dado di conferma (confirmation_dice).
- I valori di "mod" sono numerici (interi, positivi o negativi) e vengono applicati tramite somma algebrica ai rispettivi dadi.

## Esempio

```json
{
  "fucili_assalto": [
    {
      "nome": "Alta Velocità",
      "ferite": 1,
      "mod": {"confirmation_dice": 1, "hit_dice": -1}
    }
  ],
  "shotgun": [
    {
      "nome": "Pallettoni",
      "ferite": 4,
      "mod": {"hit_dice": 2}
    }
  ]
}
```
