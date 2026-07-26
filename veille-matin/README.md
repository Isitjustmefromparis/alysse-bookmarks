# Veille matin

Un mail chaque matin avec de la matière concrète pour les sujets de films en cours,
plus un ou deux items de sérendipité.

## Fichiers

| Fichier | Rôle |
|---|---|
| `sujets.md` | Les projets actifs et les angles à nourrir. **C'est le fichier à éditer.** |
| `prompt.md` | Le texte exact exécuté par la routine chaque matin. |
| `modele.html` | Le gabarit du mail, styles en ligne, palette Alysse. |
| `editions/` | Les éditions envoyées, une par jour. |

## Comment ça tourne

Une Routine Claude fait partir une session fraîche chaque matin. La session lit
`sujets.md`, recoupe avec la base Notion Projets, cherche 4 items, et produit deux
sorties :

1. un **brouillon Gmail** formaté, dans les brouillons du compte `alyssehallali@gmail.com`
2. la **notification de fin de run**, envoyée par mail, qui contient le texte brut

Le brouillon est la version à lire. La notification sert de rappel et dépanne si le
connecteur Gmail est tombé.

## Régler ce qui arrive

Tout se joue dans `sujets.md`.

- **Un projet ne remonte jamais** : ses angles sont vides ou marqués `À REMPLIR`.
  Écrire deux ou trois lignes d'angles et il entre dans la rotation.
- **Un projet remonte trop** : vider ses angles, ou le passer plus bas dans le fichier.
- **Trop de sérendipité, pas assez** : ajuster la section Sérendipité et ses terrains
  de chasse.
- **Un type de contenu revient et ne sert à rien** : l'ajouter à la section Interdits.

## Changer l'heure ou arrêter

La routine s'appelle `Veille matin - sujets de films`. Elle part à 5h10 UTC, soit
7h10 à Paris l'été et 6h10 l'hiver. Pour la modifier ou la couper, le dire en
session : `update_trigger` pour l'heure et le prompt, `delete_trigger` pour arrêter.

Si le texte du prompt change ici, il faut le répercuter dans la routine. Le fichier
`prompt.md` seul ne suffit pas : la routine embarque sa propre copie.

## Limite connue

Les fiches projet dans Notion sont vides, et Google Drive n'était pas accessible au
moment du montage. Les angles de `sujets.md` ont donc été déduits des titres de
projets. Ceux marqués `À CONFIRMER` sont des hypothèses, ceux marqués `À REMPLIR`
bloquent le projet hors rotation tant qu'ils ne sont pas renseignés.
