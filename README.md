# Agent croisière — veille îles grecques

Site statique qui affiche les résultats de la veille automatique : meilleures croisières dans les îles grecques, **septembre–octobre 2027**, **2 adultes**, **budget max 3 000 € tout compris**.
Vols depuis Paris (CDG/ORY/BVA) inclus quand le port de départ n'est ni en France ni en Italie du Nord ; sinon, pas de vol.

- `index.html` : la page (aucune dépendance, lit les fichiers de `data/`).
- `data/latest.json` : résultat de la dernière veille.
- `data/runs/AAAA-MM-JJ.json` + `data/runs/index.json` : archive des veilles (sélecteur « Veille du »).
- `data/historique.csv` : historique des prix (graphique d'évolution).

## Publication
Activer GitHub Pages : *Settings → Pages → Deploy from a branch → `main` / root*.
Le site sera visible sur https://thurtel360-bot.github.io/agent-croisiere/

## Mise à jour
Chaque jour à 7h (Paris), la tâche planifiée réécrit `data/latest.json`, ajoute `data/runs/<date>.json`, met à jour `data/runs/index.json` et `data/historique.csv`, puis pousse sur `main`.
