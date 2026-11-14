# Tallynest App Store

Community App Store per umbrelOS, creato a partire dal template ufficiale
[getumbrel/umbrel-community-app-store](https://github.com/getumbrel/umbrel-community-app-store).

| App | ID | Porta | Codice |
|---|---|---|---|
| Spese di Casa | `tallynest-expenses` | 8395 | [tallynest/home-expenses](https://github.com/febio25/home-expenses) |

## Aggiungere lo store a Umbrel

Nell'App Store di Umbrel: menu **⋯** in alto a destra → **Community App
Stores** → incolla `https://github.com/febio25/umbrel-app-store` →
**Add**. Lo store compare come «Tallynest App Store».

## Struttura

```
umbrel-app-store.yml          id e nome dello store
tallynest-expenses/
  umbrel-app.yml              scheda dell'app (nome, versione, porta)
  docker-compose.yml          container e immagine fissata con digest
  data/.gitkeep               cartella dei dati (database SQLite)
```

## Pubblicare una nuova versione

1. Nel repository del codice crea il tag della versione: GitHub Actions
   pubblica l'immagine e stampa nel riepilogo del job la riga `image:` da
   copiare.
2. Qui, in `tallynest-expenses/docker-compose.yml`, sostituisci la riga
   `image:` con quella stampata.
3. In `tallynest-expenses/umbrel-app.yml` aggiorna `version:` e, se vuoi,
   `releaseNotes:`.
4. Commit e push. Umbrel mostra l'aggiornamento nell'App Store.

Istruzioni complete nel README di
[home-expenses](https://github.com/febio25/home-expenses#readme).
