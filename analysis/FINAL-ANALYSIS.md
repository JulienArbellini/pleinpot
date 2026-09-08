# Analyse finale — sélection de la direction artistique (rounds 1 + 2)

## Résumé du processus

**Round 1** : point de départ, le retour de Clémence sur les versions V1
(brutal) et V2 (éditoriale/mix), qui rejette explicitement le "trop BD",
le "trop cute", la typo cursive et les couleurs flashy décoratives, tout
en demandant à garder l'aspect didactique, les interactions (quiz, drop),
et à ajouter une vraie galerie. Trois itérations produites (1 à 3),
l'Itération 2 "Atelier Nocturne" retenue comme meilleur score mais avec
une réserve explicite : le thème sombre pouvait se lire comme "luxe
générique", à confirmer avec Clémence.

**Round 2** : objectif explicite — produire au moins 3 directions
artistiques réellement différentes, sans s'arrêter à la première. Trois
nouvelles itérations produites (4 à 6), chacune testant une hypothèse
non explorée en round 1 : noir/blanc strict + photographie maximale
(It.4), une seule couleur signature + slab-serif (It.5), mono en display
+ motif spécimen naturaliste (It.6).

Six itérations complètes ont donc été produites au total, chacune
vérifiée dans le navigateur (desktop et mobile 375px), testée
fonctionnellement (panier, filtres, recherche, tri, quiz, countdown,
coupon, modale, menu mobile) et notée sur 9 critères avec une grille
exigeante :

| Version | Commit | Score moyen /10 | Risque principal identifié |
|---|---|---|---|
| V1 — Brutal | `bc59121` | — | Rejetée par Clémence (trop BD) |
| V2 — Éditorial (mix) | `c19a0f8` | — | Jugée "pas terrible" par Clémence |
| Itération 1 — Catalogue raisonné | `65bf9a6` | 7,3 | Trop froid/générique |
| Itération 2 — Atelier Nocturne | `d31d2f0` | 7,8 | "Luxe générique", pas assez "elle" |
| Itération 3 — Registre d'Atelier | `75215e0` | 7,6 | Recul sur la photographie |
| Itération 4 — Plein Cadre | `099de1c` | 7,6 | Dérive "marque mode" |
| Itération 5 — Signature Terracotta | `9220d52` | 7,7 | Aucun risque identitaire majeur identifié |
| Itération 6 — Carnet de Terrain | `ebb7f59` | 7,7 | Dérive "fiche technique/scientifique" |

Aucune version n'atteint un score "parfait" sur tous les critères — c'est
volontaire et documenté à chaque étape : le brief contient des exigences
qui se tirent partiellement (ex. "registre didactique compact" vs "mise
en avant très forte de la photographie"). Le rôle de cette analyse est
d'arbitrer, pas de prétendre qu'un compromis n'existe pas.

## Ce que les six itérations ont, ensemble, permis de tester

En regardant les six côte à côte, chaque itération isole une variable :

- **Fond** : clair (1, 3, 5, 6) vs sombre (2) vs noir/blanc pur (4).
- **Couleur** : aucune décorative, swatch fonctionnel par pièce (2, 3),
  zéro couleur (4), une seule couleur signature (5), duo fonctionnel à
  deux rôles (6).
- **Police display** : serif éditorial Fraunces (1, 2, 3), grotesque
  condensé façon affiche (4), slab-serif façon tampon (5), monospace
  façon carnet de terrain (6) — quatre familles totalement différentes.
- **Galerie** : masonry (1), grille alternée (2), registre/liste (3),
  plein cadre séquentiel (4), mosaïque hover-reveal (5), grille
  spécimen numérotée (6).

Cette couverture large confirme deux tensions structurelles qui
traversent tout l'exercice, jamais résolues à 100 % par une seule
version :
1. **Photographie forte vs registre didactique compact** — plus la
   galerie met en avant les images (It.4), moins elle reste scannable
   comme un inventaire (It.3 fait l'inverse).
2. **Caractère mémorable vs risque identitaire** — les versions les plus
   "spectaculaires" (It.2 sombre/luxe, It.4 mode, It.6 scientifique)
   sont aussi celles qui portent chacune un risque explicite de ne pas
   ressembler à Clémence ; les versions les plus prudentes (It.1, It.3,
   It.5) évitent ce risque mais impressionnent un peu moins au premier
   regard.

## Version retenue : **Itération 5 — "Signature Terracotta"** (`9220d52`)

### Pourquoi celle-ci plutôt qu'une autre

1. **Seule itération sur six à ne déclencher aucun risque identitaire
   majeur** dans l'auto-critique. Les cinq autres portent chacune une
   réserve explicite et différente : trop froid (1), luxe générique (2),
   recul photo (3), dérive mode (4), dérive scientifique (6). Sur un
   projet dont l'objectif central est de refléter la personnalité réelle
   de Clémence (vélo, plantes, chat, atelier bruxellois), l'absence de
   signal d'alarme identitaire pèse plus lourd qu'un dixième de point de
   score.
2. **Score parmi les plus élevés** (7,7/10, à 0,1 du maximum obtenu par
   l'Itération 2) sans le compromis que suppose ce score maximal.
3. **Meilleur équilibre chaleur/rigueur obtenu sur l'ensemble de
   l'exercice** : base crème chaude, slab-serif artisanal, une seule
   couleur de marque (terracotta, teinte de la pièce phare "Petite
   Lampe") — chaleureux sans être "cute", structuré sans être froid.
4. **Meilleure micro-interaction de galerie testée** : le hover-reveal
   de légende sur la mosaïque serrée est jugé la plus subtile et la
   plus réussie des six itérations sur ce point précis.
5. **Ne sacrifie aucune fonctionnalité** : panier, filtres, recherche,
   tri, quiz, countdown, coupon, modale, menu mobile — tout est présent
   et testé, comme demandé dès le premier brief.
6. **Aucune police supplémentaire par rapport aux itérations précédentes**
   testées à l'époque (Bitter est la seule police display propre à cette
   itération) — profil de performance raisonnable, comparable aux autres.

### Ce qui n'est PAS résolu et doit être validé avec Clémence

- L'Itération 2 reste, sur le seul critère du score chiffré et de
  l'impact visuel immédiat, légèrement devant (7,8 vs 7,7) — si
  Clémence est à l'aise avec un registre plus "galerie contemporaine
  sombre" et ne perçoit pas le risque "luxe générique" comme un
  problème pour son image, l'Itération 2 reste un choix défendable et
  mérite d'être montrée côte à côte avec l'Itération 5, exactement
  comme cela avait été fait pour V1/V2.
- La légende de galerie masquée par défaut au survol (desktop) sur
  l'Itération 5 est un vrai petit recul sur l'aspect didactique
  immédiat par rapport aux Itérations 1 et 3 — à corriger facilement en
  affichant le nom de la pièce en permanence sous chaque tuile, tout en
  gardant le hover pour la matière/année en complément.
- Le contraste texte/fond n'a été vérifié qu'à l'œil, pas avec un outil
  de contraste WCAG formel — à faire avant mise en ligne publique.

### Recommandations si l'Itération 5 est confirmée

- Rendre le nom de chaque pièce toujours visible sous les tuiles de la
  mosaïque (pas seulement au survol), pour ne pas perdre l'aspect
  didactique immédiat par rapport aux meilleures versions sur ce point.
- Vérifier le contraste texte/fond avec un outil dédié (ex. axe
  DevTools) avant mise en ligne publique.
- Envisager de sortir Tailwind du CDN (JIT navigateur) vers un build
  statique pour la performance — vrai dans les six versions, jamais
  traité dans cet exercice, hors périmètre du brief mais à garder en tête.

### Alternatives à montrer à Clémence pour trancher les questions de goût

- **Itération 2 — Atelier Nocturne** (`d31d2f0`) : si elle préfère un
  registre plus spectaculaire/sombre et n'est pas gênée par le risque
  "luxe générique".
- **Itération 6 — Carnet de Terrain** (`ebb7f59`) : si elle se reconnaît
  davantage dans l'esthétique "carnet de terrain/spécimen naturaliste"
  que dans le slab-serif chaleureux de l'Itération 5 — c'est la version
  la plus "à elle" en termes de personnalité (nature, observation,
  carnet de croquis) si le risque "trop technique" ne se vérifie pas
  à l'usage.
- **Itération 4 — Plein Cadre** (`099de1c`) : si la mise en valeur
  maximale de la photographie prime sur toute autre considération.

## État du dépôt à la fin de cet exercice

Le fichier `index.html` à la racine reflète maintenant l'**Itération 5**
(version retenue de l'ensemble des deux rounds), committée séparément
après cette analyse. Les six itérations (plus V1/V2) restent intégralement
consultables dans l'historique Git et déployables indépendamment sur
Vercel si Clémence souhaite les comparer en conditions réelles, comme
cela avait été fait pour V1/V2.
