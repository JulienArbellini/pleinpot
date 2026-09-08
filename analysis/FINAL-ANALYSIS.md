# Analyse finale — sélection de la direction artistique

## Résumé du processus

Point de départ : le retour de Clémence sur les versions V1 (brutal) et V2
(éditoriale/mix), qui rejette explicitement le "trop BD", le "trop cute",
la typo cursive et les couleurs flashy décoratives, tout en demandant à
garder l'aspect didactique, les interactions (quiz, drop), et à ajouter
une vraie galerie.

Trois itérations complètes ont été produites, chacune vérifiée dans le
navigateur (desktop 1280px, mobile 375px), testée fonctionnellement
(panier, filtres, recherche, tri, quiz, countdown, coupon, modale, menu
mobile) et notée sur 9 critères avec une grille exigeante :

| Version | Commit | Score moyen /10 | Statut |
|---|---|---|---|
| V1 — Brutal | `bc59121` | — | Rejetée par Clémence (trop BD) |
| V2 — Éditorial (mix) | `c19a0f8` | — | Jugée "pas terrible" par Clémence |
| **Itération 1** — Catalogue raisonné | `65bf9a6` | 7,3 | Base solide, un peu froide |
| **Itération 2** — Atelier Nocturne | `d31d2f0` | **7,8** | La plus forte, à valider sur un point |
| **Itération 3** — Registre d'Atelier | `75215e0` | 7,6 | La plus cohérente, mais recule sur la photo |

Aucune version n'atteint un score "parfait" sur tous les critères — c'est
volontaire et documenté à chaque étape : le brief contient des exigences
qui se tirent partiellement (ex. "registre didactique compact" vs "mise
en avant très forte de la photographie"). Le rôle de cette analyse est
d'arbitrer, pas de prétendre qu'un compromis n'existe pas.

## Version retenue : **Itération 2 — "Atelier Nocturne"** (`d31d2f0`)

### Pourquoi celle-ci et pas une autre

1. **Score le plus élevé** (7,8/10), et le plus élevé sur les deux
   critères que le brief place explicitement en tête des ajouts demandés :
   *photographie / mise en valeur des pièces* (9/10, la meilleure des
   trois) et *caractère artistique* (8/10).
2. **Résout un problème que l'Itération 1 n'avait pas résolu** : au lieu
   de reléguer la couleur réelle de Clémence au second plan (risque
   "froid/générique" identifié dans `ITERATION-1.md`), elle la réintroduit
   via un système de swatch strictement fonctionnel — chaque pièce porte
   la couleur exacte de sa propre photo, jamais en aplat décoratif. C'est
   la réponse la plus directe et la plus défendable à la règle du brief
   "éviter les couleurs flashy utilisées comme décoration" : la couleur
   sert à identifier, pas à décorer.
3. **Ne sacrifie aucune fonctionnalité** : panier, filtres, recherche,
   tri, quiz, countdown, coupon, modale, menu mobile — tout est présent et
   testé, comme demandé ("ne pas supprimer une fonctionnalité intéressante
   simplement parce qu'elle est difficile à adapter visuellement").
4. **Grille de galerie éditoriale (7/5 alterné)** plus proche de l'esprit
   "portfolio d'artiste" qu'une grille uniforme, sans sacrifier la taille
   des images comme le fait le registre de l'Itération 3.

### Ce qui n'est PAS résolu et doit être validé avec Clémence

Le score chiffré ne peut pas trancher une question de goût personnel :
- Le thème sombre est indéniablement spectaculaire et "galerie
  contemporaine", mais il peut aussi se lire comme une esthétique
  "boutique d'objets de luxe" assez générique (joaillerie, design haut de
  gamme), plus éloignée de la personnalité décontractée que Clémence
  projette sur Instagram (vélo, plantes, chat) que ne l'est un fond clair.
  **Ce point doit être confirmé directement avec elle avant mise en
  production**, idéalement en lui montrant l'Itération 2 et l'Itération 3
  côte à côte (comme cela avait été fait pour V1/V2).
- La lisibilité des graisses fines de Fraunces sur fond sombre n'a été
  vérifiée qu'à l'œil, pas avec un outil de contraste WCAG formel.

### Recommandations si l'Itération 2 est confirmée

- Ajouter la ligne matière/statut (ex. "Grès émaillé — Pièce unique") sous
  chaque entrée de galerie, présente en Itération 1 et 3 mais absente en
  Itération 2 — amélioration mineure, cohérence avec le reste du site.
- Vérifier le contraste texte/fond avec un outil dédié (ex. axe DevTools)
  avant mise en ligne publique.
- Envisager de sortir Tailwind du CDN (JIT navigateur) vers un build
  statique pour la performance — vrai dans les quatre versions, jamais
  traité dans cet exercice, hors périmètre du brief mais à garder en tête.

### Alternative si Clémence préfère un fond clair

**Itération 3 — Registre d'Atelier** (`75215e0`) est le meilleur candidat
de repli : même système de swatch, cohérence la plus aboutie des trois,
countdown moins "hype". Il faudrait alors élargir les vignettes de la
galerie (actuellement 64–96px, trop petites au regard de l'exigence de
mise en valeur photographique) — par exemple en gardant le principe de
liste numérotée mais avec une image occupant toute la largeur de chaque
ligne plutôt qu'une vignette carrée, ce qui n'a pas été testé dans cet
exercice.

## État du dépôt à la fin de cet exercice

Le fichier `index.html` à la racine reflète maintenant l'**Itération 2**
(version retenue), committée séparément après cette analyse. Les trois
itérations restent intégralement consultables dans l'historique Git
(`git show 65bf9a6:index.html`, `d31d2f0:index.html`, `75215e0:index.html`)
et déployables indépendamment sur Vercel si Clémence souhaite les comparer
en conditions réelles, comme cela avait été fait pour V1/V2.
