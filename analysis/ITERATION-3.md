# Itération 3 — "Registre d'Atelier"

## Concept

Synthèse assumée des deux itérations précédentes plutôt qu'une troisième
direction radicalement inédite : fond clair chaleureux (comme l'Itération 1,
pour écarter le risque "froid/luxe" du thème sombre) + système de swatch
fonctionnel (validé en Itération 2). La vraie nouveauté structurelle porte
sur la **galerie**, transformée en registre/liste façon inventaire de
musée plutôt qu'en grille d'images (masonry en It.1, grille alternée en
It.2) — chaque pièce devient une ligne numérotée avec vignette, nom, point
de couleur, matière et année.

## Ce qui a été changé

- Retour au fond papier clair (#F7F5F0 / #1C1A17), abandon du thème sombre.
- Système de `swatch` par pièce conservé et étendu (utilisé aussi dans le
  graphique du temps de fabrication, recoloré avec les teintes exactes).
- **Galerie reconstruite en registre/liste** : numéro (01, 02…), vignette
  modeste, nom, point de couleur, matière/statut, année, flèche — lecture
  verticale façon inventaire, pas grille d'images.
- **Compte à rebours compacté** : `03j · 14h · 22m · 45s` en une seule
  ligne typographique dense, au lieu de grands chiffres façon minuteur —
  réduit délibérément la tonalité "urgence e-commerce" du countdown.
- Filtres boutique : reprise de la pastille pleine (correctif de
  l'Itération 2) dès la conception initiale, pas ajoutée après-coup.
- **Correctif appliqué avant commit** : le panneau de menu mobile hérite
  de la transparence du header (`bg-paper/95` + `backdrop-blur`), ce qui
  laissait transparaître le contenu de la page derrière lui — fond opaque
  dédié ajouté.

## Ce qui fonctionne

- Le registre répond très directement à "l'aspect didactique" et à la
  "sensation de portfolio/archive d'artiste" que Clémence apprécie déjà
  et demande explicitement — c'est la version la plus proche d'un
  catalogue raisonné réel (numérotation, matière, année en colonne).
- Combine les deux points forts validés séparément : chaleur du fond clair
  (moins de risque "corporate/luxe" que l'Itération 2) et couleur comme
  repère fonctionnel plutôt que décoration (hérité de l'Itération 2).
- Le countdown compact retire une bonne partie du ton "hype drop" sans
  supprimer la fonctionnalité — répond à la tension notée dans l'analyse
  de l'Itération 2 sans sacrifier "le prochain drop" que Clémence apprécie.
- Cohérence visuelle la plus aboutie des trois itérations : rien ne
  détonne d'une section à l'autre.
- Toutes les fonctionnalités testées, aucune erreur console, mobile
  vérifié (y compris le correctif d'opacité du menu).

## Ce qui ne fonctionne pas (auto-critique sévère)

- **Contradiction avec une exigence explicite du brief.** Le brief demande
  "une mise en avant beaucoup plus forte de la photographie". Les
  vignettes du registre (64–96px) sont nettement plus petites que les
  images pleine largeur des galeries en grille des Itérations 1 et 2.
  Sur ce critère précis, cette itération **recule** par rapport aux deux
  précédentes plutôt que de progresser — c'est un vrai défaut, pas un
  simple compromis esthétique neutre.
- **Moins structurellement "nouvelle" que ne l'était l'Itération 2.**
  L'écart entre It.1 et It.2 (clair→sombre, masonry→grille alternée,
  couleur décorative→fonctionnelle) était plus net que l'écart entre
  It.2 et It.3 (même palette de couleurs, même typographie, seule la
  galerie et le countdown changent réellement). Cette itération est une
  synthèse assumée, pas une troisième direction indépendante — à nommer
  clairement plutôt qu'à présenter comme équivalente en radicalité.
- Le countdown compact, bien que plus sobre, est aussi **moins visible au
  premier coup d'œil** — pour une fonctionnalité que Clémence dit apprécier
  spécifiquement, la discrétion a un coût potentiel sur l'engagement.
- Troncature des noms longs dans le registre sur mobile (`Théière «
  Petite ...`) — acceptable mais pas idéal, un survol/tap est nécessaire
  pour lire le nom complet.

## Score détaillé (sur 10, exigeant)

| Critère | Score | Justification courte |
|---|---|---|
| Direction artistique | 8 | Meilleure synthèse des contraintes, mais moins radicalement "nouvelle" que It.2 |
| Qualité typographique | 8 | Système éprouvé une troisième fois, traitement du countdown particulièrement soigné |
| Photographie / mise en valeur | 6 | Recul net par rapport à It.1/It.2 sur une exigence explicite du brief |
| UX | 8 | Corrections cumulées (filtres, menu mobile) appliquées dès la conception |
| Interactivité | 7 | Fonctionnalités intactes, registre scannable au survol |
| Caractère artistique | 7 | Sensation "inventaire d'atelier" forte, mais visuellement moins spectaculaire que It.2 |
| Cohérence | 9 | La plus aboutie des trois itérations |
| Mobile | 8 | Testé, correctif d'opacité du menu inclus |
| Performance | 7 | Toujours Tailwind CDN, inchangé |

**Moyenne : 7,6 / 10**

## Comparaison avec V1 / V2 / Itération 1 / Itération 2

| Version | Score moyen | Point fort | Point faible |
|---|---|---|---|
| V1 Brutal | — (rejetée) | — | BD, e-commerce générique |
| V2 Éditorial (mix) | — ("pas terrible") | — | Cursive, encore trop "cute" par endroits |
| Itération 1 — Catalogue raisonné | 7,3 | Rupture nette avec le e-commerce | Trop froid/générique par endroits |
| Itération 2 — Atelier Nocturne | **7,8** | Photographie, caractère | Risque "luxe générique", à valider avec Clémence |
| Itération 3 — Registre d'Atelier | 7,6 | Cohérence, aspect didactique/archive | Recul sur la mise en avant photo |

Aucune itération n'obtient un score parfait sur tous les critères — c'est
attendu : "photographie forte" et "registre didactique compact" sont
deux exigences du brief qui tirent la mise en page dans des directions
partiellement contradictoires. Le choix final dépend de la priorité
relative que Clémence accorde à l'une ou l'autre — développé dans
`FINAL-ANALYSIS.md`.
