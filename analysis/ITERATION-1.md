# Itération 1 — "Catalogue raisonné"

Commit de référence : voir `git log` juste après ce fichier (message
"Itération 1 — Catalogue raisonné").

## Concept

Rupture nette avec le langage brutaliste/e-commerce des versions V1 et V2 :
fond neutre (papier #F7F5F0 / encre #1C1A17), typographie serif éditoriale
(Fraunces) + sans neutre (Inter) + mono pour les métadonnées (IBM Plex Mono).
Suppression totale de la couleur comme décoration — les vraies couleurs de
Clémence (fuchsia, cobalt, terracotta, sauge, moutarde) ne survivent que
dans le graphique du temps de fabrication, où elles codent une donnée.

## Ce qui a été changé

- Suppression complète de la police cursive (Caveat), des stickers/badges
  colorés, des bordures noires épaisses et ombres "brutal" décoratives.
- Suppression du bandeau/de tout emoji dans l'interface et les messages
  (`alert()` du checkout, du coupon, de l'inscription VIP compris).
- **Nouvelle section Galerie** : masonry CSS (colonnes, sans JS) présentant
  les 6 pièces en grand format avec légendes façon cartel de musée
  (N°, nom, matière, année, statut).
- Boutique restylée : cartes sans cadre, badge en italique discret, bouton
  "+" qui n'apparaît qu'au survol.
- Compte à rebours : chiffres serif nus, plus de bloc de couleur plein.
- Quiz : cartes de réponse sobres (bordure fine, état sélectionné = bordure
  foncée), plus d'emoji ni de couleur de fond au survol.
- Atelier : mêmes photos et mêmes 4 étapes, numéros en grand serif au lieu
  de badges colorés.
- **Correctif d'image** : `product-mug-le-mont.jpg` recadrée pour retirer
  le texte "A mountain mug" incrusté (hérité d'Instagram), incompatible
  avec le ton catalogue sérieux visé.
- **Correctif UX** : ajout d'un menu mobile (bouton hamburger + panneau) —
  la nav était `hidden` sous 768px sans aucune alternative dans le code
  hérité de V2, ce qui rendait Galerie/Atelier/Drop/Quiz inaccessibles au
  clavier/scroll rapide sur mobile.
- **Correctif de code** : `selectQuiz` reposait sur la variable globale
  implicite `window.event` (fonctionne dans Chrome, pas garanti ailleurs) ;
  passage explicite de l'événement en paramètre.

## Ce qui fonctionne

- L'objectif premier du brief est atteint : plus aucune trace de BD, de
  cursive, de mignon. Le site se lit clairement comme un catalogue/portfolio.
- La galerie masonry est une vraie nouveauté qui répond directement à la
  demande de Clémence ("une page présentant toutes les pièces") — jamais
  présente dans V1/V2.
- Les cartels (matière, année, statut) donnent une vraie sensation
  d'archive d'artiste, cohérente avec le côté didactique qu'elle apprécie.
- Toutes les fonctionnalités (panier, filtres, recherche, tri, quiz,
  countdown, coupon, modale) sont préservées et testées manuellement dans
  le navigateur — aucune régression.
- Aucune erreur console sur l'ensemble du parcours testé.

## Ce qui ne fonctionne pas (auto-critique sévère)

- **Risque de sur-correction vers le froid/corporate.** En reléguant sa
  palette réelle au seul graphique, le site perd une partie de ce qui la
  rend "elle" — on est passé de "boutique Instagram mignonne" à quelque
  chose qui pourrait se lire comme un site Squarespace minimaliste
  générique. Le brief interdit explicitement les deux écueils ; celui-ci
  n'est qu'à moitié évité.
- **Affordance faible de certains éléments interactifs.** Les CTA en simple
  soulignement fin (bouton "S'inscrire →" du drop, filtres de catégorie)
  peuvent se lire comme du texte inerte plutôt que comme des actions,
  surtout pour un public non averti visitant depuis mobile.
- **Contraste des bordures fines** (`border-ink/20`) potentiellement trop
  léger sur certains fonds — à vérifier avec un outil de contraste avant
  mise en production réelle (non testé formellement ici).
- **Inter est un choix de police extrêmement neutre**, utilisé par des
  milliers de produits SaaS — il fait le travail mais n'ajoute aucune
  personnalité propre à Plein Pot ; le duo Fraunces/Inter est solide mais
  "sûr", pas mémorable en soi.
- La grille boutique garde un recadrage carré uniforme — cohérent pour du
  e-commerce, mais moins "portfolio" que la galerie juste au-dessus ;
  léger décalage de ton entre les deux sections consécutives.

## Score détaillé (sur 10, exigeant)

| Critère | Score | Justification courte |
|---|---|---|
| Direction artistique | 7 | Rupture nette réussie avec V1/V2, mais bascule vers un minimalisme un peu trop sûr/impersonnel |
| Qualité typographique | 8 | Fraunces/Inter/Plex Mono cohérents, hiérarchie claire, zéro cursive |
| Photographie / mise en valeur | 8 | La galerie masonry est la vraie réussite de cette itération |
| UX | 7 | Fonctionnel et corrigé (mobile nav), mais affordance de certains CTA trop discrète |
| Interactivité | 7 | Tout est préservé et fonctionnel, esthétique sobre comme demandé |
| Caractère artistique | 6 | Le point faible : manque encore une signature propre à Plein Pot |
| Cohérence | 8 | Le système tient sur l'ensemble du site sans rupture de ton |
| Mobile | 8 | Bon après correction du menu ; testé à 375px |
| Performance | 7 | Toujours Tailwind CDN (JIT navigateur) — inchangé par rapport à V2, pas optimisé |

**Moyenne : 7,3 / 10**

## Comparaison avec V1 / V2

- Élimine tous les points négatifs cités par Clémence (BD, cute,
  Instagram, cursive) — bien plus radicalement que ne le faisait V2.
- Ajoute la galerie qu'elle demandait explicitement et qui n'existait dans
  aucune version précédente.
- Perd en chemin une partie de la chaleur colorée que V2 avait justement
  essayé de construire à partir de ses propres photos — un aller trop loin
  dans l'autre sens.

## À améliorer pour la prochaine itération

Explorer une direction qui **réintroduit sa palette réelle comme matière
graphique légitime** (pas décorative, pas "flashy") — par exemple via une
mise en page qui s'inspire davantage de la mise en scène couleur de ses
propres photos (aplats posés avec intention, pas en fond de section), tout
en gardant la rigueur typographique et l'absence de cursive/stickers de
cette itération. Renforcer aussi l'affordance visuelle des CTA secondaires.
