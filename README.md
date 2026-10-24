# gta6-watch

Surveille la précommande **GTA VI (Code in a Box, Xbox Series)** sur [E.Leclerc](https://www.e.leclerc/fp/grand-theft-auto-vi-code-in-a-box-xbox-series-5026555370103) et envoie une notif sur le téléphone via [ntfy](https://ntfy.sh) quand elle redevient dispo.

## Fonctionnement

- GitHub Actions lance un check **toutes les 5 min, de 9h à minuit (heure Algérie)**.
- Le script lit la page produit : si « épuisé / indisponible » disparaît, c'est dispo.
- Notifs :
  - 🚨 **Dispo** : urgente, renvoyée à chaque check tant que c'est dispo (tap = ouvre la page)
  - ⏳ **Point horaire** : « rien pour l'instant », une fois par heure
  - ⚠️ **Bloqué** : si Leclerc bloque la vérif depuis GitHub (max 1 par heure)

## Config

- Secret du repo `NTFY_TOPIC` = nom du topic ntfy
- S'abonner au même topic dans l'app ntfy

## Commandes utiles

- **Tester** : onglet Actions → *GTA VI Leclerc watch* → *Run workflow* (case test cochée)
- **Arrêter** : onglet Actions → *GTA VI Leclerc watch* → `⋯` → *Disable workflow*

Fichier : [`.github/workflows/gta6.yml`](.github/workflows/gta6.yml)
