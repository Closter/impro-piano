# Impro soul au piano

Petite application web pour s'entraîner à improviser au piano (blues, soul) :
grilles d'accords, gammes et notes conseillées sur un clavier, accompagnement réglable,
et mode écoute : l'app reconnaît au micro l'accord joué et affiche les notes pour improviser.

L'application tourne entièrement dans le navigateur, sans serveur, et marche hors ligne une fois installée.

## Utiliser l'application

Ouvrir `https://closter.github.io/impro-piano/`, puis l'installer :
- **iPhone / iPad** : Safari > Partager > « Sur l'écran d'accueil »
- **Android** : Chrome > menu > « Installer l'application »

## Structure

| Fichier | Rôle |
|---|---|
| `index.html` | L'application (HTML, CSS et JavaScript) |
| `manifest.json` | Nom, icônes et couleurs pour l'installation |
| `sw.js` | Service worker : cache hors ligne |
| `icons/` | Icônes de l'application |

## Publier une mise à jour

1. Modifier les fichiers.
2. Dans `sw.js`, incrémenter `CACHE` (par exemple `impro-v1` → `impro-v2`).
3. Faire un commit et un push sur `main` : GitHub Pages republie en une minute environ.

## Mode écoute

Le micro est analysé localement, dans le navigateur (rien n'est envoyé). Le spectre est converti en énergie des 12 notes,
en retirant les harmoniques, puis comparé à des modèles d'accords (majeur, mineur, 7, m7, maj7). Un accord n'est affiché
qu'après environ 0,3 s de détection stable. L'option « Main gauche seulement » n'analyse que les notes jusqu'au Do du milieu.

## Données

Les réglages sont stockés localement dans le navigateur de chaque appareil.
Aucune adresse de serveur ni aucune clé ne doit être écrite dans ce dépôt (il est public).
