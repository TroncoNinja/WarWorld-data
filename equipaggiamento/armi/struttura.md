# Struttura dati armi

Descrive il formato del file JSON che elenca le armi suddivise per categoria e le loro statistiche base.

## Schema concettuale

```
{
  "categoria": [
    {
      "nome": string,         // nome dell'arma
      "hand": number,         // bonus/malus corpo a corpo
      "short": number,        // bonus/malus a corta distanza
      "medium": number,       // bonus/malus a media distanza
      "long": number          // bonus/malus a lunga distanza
    }
  ],
  ...altre categorie
}
```

## Regole
- Tutte le statistiche sono interi >= 0.
- Le categorie (es: "fucili_assalto", "shotgun", ecc.) sono chiavi univoche.
- Ogni arma deve avere tutti i campi obbligatori.
- I valori rappresentano modificatori o efficacia per distanza.

## Esempio

```json
{
  "fucili_assalto": [
    {
      "nome": "AK-74",
      "hand": 0,
      "short": 2,
      "medium": 1,
      "long": 0
    }
  ],
  "pistole": [
    {
      "nome": "Glock 17",
      "hand": 2,
      "short": 1,
      "medium": 0,
      "long": 0
    }
  ]
}
```