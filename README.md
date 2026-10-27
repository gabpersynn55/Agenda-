# Agenda TAGE MAGE

Agenda perso : 2 h de TAGE MAGE par jour placées autour des cours ICAM (jusqu'au 3 février 2027) et le plan 10 km (52 séances). Fonctionne hors ligne une fois installé sur l'iPhone.

## Contenu du dossier

| Fichier | Rôle |
|---|---|
| `index.html` | L'application complète (emploi du temps, plan course, réglages) |
| `manifest.json` | Nom, icône et couleurs de l'app installée |
| `sw.js` | Service worker : fonctionnement hors ligne et mises à jour |
| `icon-*.png` | Icônes de l'écran d'accueil |

## 1. Créer le dépôt

1. Sur github.com : **New repository**.
2. Nom : `agenda-tm` (ou ce que tu veux). Visibilité : **Public** (GitHub Pages gratuit l'exige).
3. Clique sur **Create repository**.
4. Sur la page du dépôt : **Add file → Upload files**, glisse **tous les fichiers de ce dossier** (pas le dossier lui-même), puis **Commit changes**.

## 2. Activer GitHub Pages

1. Dans le dépôt : **Settings → Pages**.
2. Source : **Deploy from a branch**. Branch : **main**, dossier **/ (root)**. **Save**.
3. Attends 1 à 2 minutes. L'adresse apparaît en haut de la page : `https://TON-PSEUDO.github.io/agenda-tm/`

## 3. Installer sur l'iPhone

1. Ouvre l'adresse dans **Safari** (pas Chrome).
2. Bouton **Partager** → **Sur l'écran d'accueil** → **Ajouter**.
3. Lance l'app depuis l'icône **Agenda TM** une première fois avec du réseau : elle se met en cache et marche ensuite hors ligne.

## 4. Mettre à jour l'app

1. Remplace `index.html` sur GitHub (Upload files, même nom).
2. Ouvre `sw.js`, change la ligne `const VERSION = 'v1';` en `'v2'` (puis `'v3'`, etc.) et remplace-le aussi.
3. Sur l'iPhone, ouvre l'app avec du réseau : elle se recharge toute seule sur la nouvelle version (sinon ferme-la et rouvre-la).

Tes coches, déplacements et réglages sont conservés pendant les mises à jour.

## Sauvegarde

Les données restent **dans l'iPhone**, dans l'app installée (pas dans Safari ni sur GitHub). Pense à faire de temps en temps **Réglages → Exporter ma sauvegarde** pour garder une copie.

## Modifier les données

En haut du `<script>` dans `index.html` :

- `COURS` : l'emploi du temps ICAM (une ligne par cours). Ou plus simple : **Réglages → Importer un nouvel emploi du temps**.
- `RUNS` : le plan 10 km (date, titre, durée en minutes, détail).
- `EXCEPTIONS` : les jours particuliers (ex. `'2026-11-09':{daily:240}` pour 4 h ce jour-là).
- `SPECIAL` : session blanche du 19/11 et jour J du 4 février.
