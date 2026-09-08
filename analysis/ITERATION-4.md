# Itération 4 — "Plein Cadre"

## Concept

Rupture radicale avec les trois itérations précédentes (toutes construites
sur une base "papier + serif éditorial", claire ou sombre) : ici, interface
strictement noir/blanc, typographie condensée façon affiche de cinéma
("Big Shoulders Display"), et surtout **aucune couleur nulle part dans
l'interface** — la seule couleur du site est celle des photographies
elles-mêmes (non désaturées, contrairement au hero qui lui passe en
`grayscale`). La galerie devient un défilement plein cadre, une pièce à la
fois, en alternance gauche/droite, à très grande échelle (60–80vh par image).

## Ce qui a été changé

- Palette réduite à trois valeurs : blanc, noir, gris clair (bordures) —
  zéro accent coloré décoratif ou fonctionnel, contrairement aux trois
  itérations précédentes qui utilisaient toutes un système de couleur
  (swatch) même minimal.
- Typo display remplacée : "Big Shoulders Display" (grotesque condensé,
  registre affiche) au lieu de Fraunces (serif éditorial) utilisé dans les
  itérations 1 à 3 — première itération qui change réellement de famille
  de caractères plutôt que de seulement changer les couleurs autour.
- Hero plein cadre (`h-[92vh]`, image en `grayscale`, texte énorme en
  surimpression) au lieu d'un hero en deux colonnes texte/image.
- Galerie reconstruite en défilement séquentiel plein cadre (une pièce =
  un bloc image + texte, alterné), différent du masonry (It.1), de la
  grille alternée (It.2) et du registre en liste (It.3).
- Tous les cadres/bordures redeviennent de simples traits fins fonctionnels
  (`border border-ink`), jamais décoratifs.
- **Correctifs appliqués avant commit** :
  - bug détecté en test mobile : le texte du hero ("VIVANTS") était
    partiellement masqué par les boutons CTA positionnés en `absolute
    bottom` sans tenir compte de la hauteur variable du titre sur petit
    écran — CTA replacés dans le flux normal sous le titre ;
  - orpheline typographique : le guillemet fermant (« » ») des noms de
    pièces pouvait se retrouver seul en début de ligne dans les gros
    titres de la galerie — espace insécable ajoutée avant le guillemet.

## Ce qui fonctionne

- **La meilleure mise en valeur photographique des six versions produites
  à ce jour** (V1/V2 + Itérations 1 à 4) : les images occupent 60 à 92%
  de la hauteur d'écran, et le contraste "interface totalement neutre /
  photo pleinement saturée" fait ressortir les couleurs réelles de
  Clémence (lavande, corail, magenta) bien plus que dans une interface
  déjà colorée. Répond au maximum à l'exigence du brief "mise en avant
  beaucoup plus forte de la photographie".
- Aucune ambiguïté possible avec "boutique Instagram" ou "template
  e-commerce" — l'esthétique est sans équivoque celle d'un lookbook ou
  d'une publication de mode/design.
- Toutes les fonctionnalités testées et opérationnelles (panier, filtres,
  recherche, tri, quiz avec état sélectionné, countdown, coupon, modale,
  menu mobile), aucune erreur console.
- Le graphique du temps de fabrication reste cohérent avec le reste :
  entièrement en niveaux de gris.

## Ce qui ne fonctionne pas (auto-critique sévère)

- **Risque de dérive vers "marque mode/streetwear" plutôt que "atelier de
  céramique".** La typographie condensée en capitales et le noir/blanc
  strict évoquent davantage une marque de mode ou un magazine de design
  qu'un atelier artisanal chaleureux. C'est esthétiquement le plus
  "confiant" des quatre itérations, mais aussi celui qui s'éloigne le
  plus du ton personnel et décontracté de Clémence (vélo, plantes, chat).
  À vérifier explicitement avec elle — le risque est réel, pas hypothétique.
- **Recul sur l'aspect didactique.** Le format "une pièce, plein cadre"
  privilégie l'impact visuel sur l'information : comparé au registre de
  l'Itération 3 (numéro, matière, année en un coup d'œil pour toutes les
  pièces), il faut ici scroller beaucoup plus longtemps pour parcourir
  l'ensemble de la collection. Page totale ~14 000px de haut contre
  ~6 000–8 000px pour les itérations précédentes — fatigue de défilement
  possible avant d'atteindre la boutique.
- Deux bugs réels trouvés en test (chevauchement mobile du hero, orpheline
  typographique) — corrigés avant commit, mais leur présence initiale
  montre que cette mise en page à fort contraste d'échelle (texte en vw,
  images en vh) est plus fragile aux cas limites que les grilles plus
  conventionnelles des itérations précédentes.
- Perte totale du système de couleur fonctionnelle (swatch) introduit en
  Itération 2 et jugé être l'un des meilleurs apports du processus —
  ici, aucune couleur d'identité par pièce dans l'interface elle-même.

## Score détaillé (sur 10, exigeant)

| Critère | Score | Justification courte |
|---|---|---|
| Direction artistique | 8 | La plus audacieuse et distinctive, mais risque réel de sur-aligner vers "mode" plutôt que "céramique" |
| Qualité typographique | 7 | Beau contraste serif→grotesque condensé, mais deux bugs typographiques trouvés en test |
| Photographie / mise en valeur | 10 | La meilleure des six versions produites sur ce critère précis |
| UX | 6 | Défilement très long, bug de chevauchement mobile trouvé (corrigé) |
| Interactivité | 7 | Fonctionnalités intactes, sobres, cohérentes avec le parti pris minimal |
| Caractère artistique | 8 | Très mémorable, mais interroge sur l'adéquation avec "elle" plus que toute autre itération |
| Cohérence | 8 | Système tenu du hero au footer, y compris le graphique |
| Mobile | 7 | Fonctionnel après correctif, mais le défilement long pénalise plus sur petit écran |
| Performance | 7 | Toujours Tailwind CDN, inchangé ; police supplémentaire chargée (Big Shoulders Display) |

**Moyenne : 7,6 / 10**

## Comparaison avec les versions précédentes

| Version | Score moyen /10 |
|---|---|
| Itération 1 — Catalogue raisonné | 7,3 |
| Itération 2 — Atelier Nocturne | 7,8 |
| Itération 3 — Registre d'Atelier | 7,6 |
| **Itération 4 — Plein Cadre** | **7,6** |

Égale l'Itération 3 en score moyen, mais avec un profil radicalement
différent : elle gagne massivement sur la photographie (10 vs 6) et perd
sur l'UX/le caractère didactique (6 vs 8). Confirme que "photographie
forte" et "parcours didactique rapide" restent les deux pôles entre
lesquels chaque direction doit choisir — aucune version testée jusqu'ici
ne résout complètement cette tension.

## À améliorer pour la prochaine itération

Explorer une direction qui teste une **troisième famille typographique et
un troisième rapport à la couleur**, différents des deux déjà testés
(serif éditorial + swatch multicolore ; grotesque condensé N&B) — par
exemple une seule couleur signature au lieu de plusieurs (hypothèse non
testée), pour voir si une identité de marque plus simple à mémoriser
résout une partie du risque "dérive mode" sans revenir à un système de
couleur multiple.
