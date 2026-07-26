# Veille matin

Un mail chaque matin avec de la matière concrète pour les sujets des projets en cours,
plus un ou deux items de sérendipité.

## Fichiers

| Fichier | Rôle |
|---|---|
| `sujets.md` | Les projets et les angles à nourrir. **C'est le fichier à éditer.** |
| `prompt.md` | Le texte exact exécuté par la routine chaque matin. |
| `modele.html` | Le gabarit du mail, styles en ligne, palette Alysse. |
| `editions/` | Les éditions envoyées, une par jour. Sert aussi à éviter les redites. |

## Comment ça tourne

Une Routine Claude fait partir une session fraîche chaque matin. La session lit
`sujets.md`, cherche 4 items, et produit deux sorties :

1. un **brouillon Gmail** formaté, dans les brouillons de `alyssehallali@gmail.com`
2. la **notification de fin de run**, envoyée par mail, qui contient le texte brut

Le brouillon est la version à lire. La notification sert de rappel et dépanne si le
connecteur Gmail est tombé.

Les sujets viennent uniquement de `sujets.md`. La base Notion de suivi n'est pas
consultée : elle donne des états de contrat et des dates de rendu, pas des sujets.

## Régler ce qui arrive

Tout se joue dans `sujets.md`.

- **Un projet ne remonte jamais** : ses angles sont vides. Écrire deux ou trois lignes
  d'angles et il entre dans la rotation.
- **Un projet remonte trop** : vider ses angles, ou en retirer.
- **Les items tombent à côté** : les angles sont trop larges. Remplacer une ligne vague
  par une ligne précise, le mail suit immédiatement.
- **Un type de contenu revient et ne sert à rien** : l'ajouter à la section Interdits.
- **Nouveau projet** : dupliquer le bloc `Autre projet`, deux lignes de contexte puis
  les angles.

## Changer l'heure ou arrêter

La routine s'appelle `Veille matin - sujets de films`. Elle part à 5h10 UTC, soit
7h10 à Paris l'été et 6h10 l'hiver. Pour la modifier ou la couper, le dire en
session : `update_trigger` pour l'heure et le prompt, `delete_trigger` pour arrêter.

Si le texte du prompt change ici, il faut le répercuter dans la routine. Le fichier
`prompt.md` seul ne suffit pas : la routine embarque sa propre copie.
