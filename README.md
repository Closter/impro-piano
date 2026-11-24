# Impro soul au piano

Petite application web pour s'entraîner à improviser au piano (blues, soul) :
grilles d'accords, gammes et notes conseillées sur un clavier, accompagnement réglable.

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

## Données

Les réglages sont stockés localement dans le navigateur de chaque appareil.
Aucune adresse de serveur ni aucune clé ne doit être écrite dans ce dépôt (il est public).
