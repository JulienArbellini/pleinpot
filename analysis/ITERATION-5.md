# Itération 5 — "Signature Terracotta"

## Concept

Troisième hypothèse de système chromatique, différente des deux déjà
testées : ni la palette multicolore par pièce (swatch, Itération 2), ni
le noir/blanc total (Itération 4), mais **une seule couleur de marque**
(terracotta #B8471E, la teinte de la pièce phare "Petite Lampe") posée
sur une base crème chaude et une encre brun-noir plutôt que noir pur.
Troisième famille typographique testée : "Bitter", un slab-serif épais
qui évoque le tampon, l'estampille, l'objet pressé — une personnalité
différente du serif éditorial fin (Fraunces, It.1-3) et du grotesque
condensé façon affiche (Big Shoulders, It.4). Galerie reconstruite en
mosaïque serrée (grille sans espacement) avec légende révélée au survol.

## Ce qui a été changé

- Palette : crème chaud (#FBF3EA), encre brun-noir (#2B211A), une seule
  couleur signature (#B8471E) utilisée pour tous les accents fonctionnels
  (liens, CTA, countdown, bordures actives) — pas de variation par pièce.
- Typo display : Bitter (slab-serif), remplace Fraunces et Big Shoulders
  Display des itérations précédentes.
- Sections Drop et Quiz basculent sur fond encre (contraste chaud/sombre
  ponctuel) plutôt que rester sur le fond crème comme le reste du site —
  rythme de page différent des itérations précédentes qui gardaient un
  fond unique du haut en bas (It.1, It.3) ou basculaient entièrement (It.2).
- Galerie en mosaïque serrée (`gap-1`, sans marge), légende en overlay
  dégradé révélée au survol (desktop) ou toujours visible sous 640px.
- Cadre fin décalé (2px, couleur signature) derrière la photo du hero —
  seul motif "décoratif" du site, choix délibérément mesuré pour rester
  loin du registre "brutal" rejeté par Clémence.

## Ce qui fonctionne

- **Le meilleur équilibre chaleur/rigueur obtenu jusqu'ici.** Contrairement
  à l'Itération 2 (risque "luxe générique") et à l'Itération 4 (risque
  "marque mode"), celle-ci ne déclenche aucune alarme évidente sur le
  "trop froid" ni sur le "pas elle" — la base crème et le slab-serif
  donnent un ton artisanal immédiatement identifiable.
- Le survol de la mosaïque de galerie fonctionne parfaitement (vérifié à
  une largeur >640px) : légende qui glisse depuis le bas sur un dégradé,
  interaction subtile et non gadget, exactement dans l'esprit demandé.
- Toutes les fonctionnalités testées par clic direct (pas seulement par
  appel JS) : filtres, panier, modale, ajout au panier, quiz avec les
  deux questions cliquées à la souris — tout fonctionne, recommandation
  correcte affichée.
- Aucune erreur console sur l'ensemble du parcours.

## Ce qui ne fonctionne pas (auto-critique sévère)

- **Incohérence entre couleur d'accent et couleur réelle de la pièce.**
  Le badge "Nouveauté" du Bol piédestal (glaçure bleu-gris) s'affiche en
  terracotta comme tous les autres — contrairement au système de swatch
  de l'Itération 2, la couleur de marque ne correspond plus à la pièce
  qu'elle accompagne. C'est cohérent comme identité de marque unique,
  mais on perd la justesse "couleur = identité réelle de la pièce" que
  Clémence pourrait remarquer en comparant les versions.
- **Légende de galerie masquée par défaut sur desktop.** Contrairement
  aux Itérations 1 et 3 (nom toujours visible), il faut survoler chaque
  tuile pour connaître le nom de la pièce — léger recul sur l'aspect
  didactique/immédiat par rapport aux meilleures versions sur ce point,
  compensé partiellement par l'affichage permanent en dessous de 640px.
- Slab-serif "Bitter" est un choix típographique plus consensuel/attendu
  (courant sur les blogs et sites éditoriaux) que Fraunces ou Big
  Shoulders — pertinent et chaleureux, mais moins "signature" que les
  deux polices display testées précédemment.
- Anomalie observée pendant les tests : après avoir cliqué les deux
  réponses du quiz à la souris, la page s'est retrouvée en haut de
  l'écran de façon inattendue avant que je ne re-scrolle manuellement
  vers le résultat — le state JS (`quizAnswers`) était pourtant correct
  et le rendu final bon. Je n'ai pas pu déterminer avec certitude si
  c'est un comportement du site (ex. `scrollIntoView` implicite quelque
  part) ou un artefact de l'outil de test ; à surveiller si le problème
  se reproduit en usage réel.

## Score détaillé (sur 10, exigeant)

| Critère | Score | Justification courte |
|---|---|---|
| Direction artistique | 8 | Meilleur équilibre chaleur/rigueur des cinq itérations, aucun signal d'alarme évident |
| Qualité typographique | 7 | Bitter est solide et chaleureux mais plus consensuel que les choix précédents |
| Photographie / mise en valeur | 8 | Mosaïque serrée efficace, légère perte d'information par défaut (hover) |
| UX | 8 | Tout fonctionne, testé par clic direct ; anomalie de scroll non confirmée comme bug réel |
| Interactivité | 8 | Hover-reveal de la galerie est la meilleure micro-interaction testée à ce jour |
| Caractère artistique | 7 | Chaleureux et cohérent, mais moins immédiatement mémorable qu'It.2 ou It.4 |
| Cohérence | 8 | Système tenu du header au footer |
| Mobile | 8 | Testé, légendes toujours visibles en dessous de 640px (bon choix de repli) |
| Performance | 7 | Toujours Tailwind CDN, une police supplémentaire (Bitter) |

**Moyenne : 7,7 / 10**

## Comparaison avec les versions précédentes

| Version | Score moyen /10 | Risque principal identifié |
|---|---|---|
| Itération 1 — Catalogue raisonné | 7,3 | Trop froid/générique |
| Itération 2 — Atelier Nocturne | 7,8 | "Luxe générique", pas assez "elle" |
| Itération 3 — Registre d'Atelier | 7,6 | Recul sur la photographie |
| Itération 4 — Plein Cadre | 7,6 | Dérive "marque mode" |
| **Itération 5 — Signature Terracotta** | **7,7** | Perte de la couleur-par-pièce ; légende masquée par défaut |

Cette itération est la seule des cinq à ne déclencher **aucun risque
identitaire majeur** dans l'auto-critique — les quatre précédentes ont
chacune un point d'interrogation assez net sur l'adéquation avec la
personnalité de Clémence (trop froid, trop luxe, trop mode) ou sur le
respect strict du brief (recul photo). Signature Terracotta est un
compromis plus prudent, ce qui explique son bon score sans pic
spectaculaire sur aucun critère.

## À améliorer pour la prochaine itération

Tester si la richesse du swatch multicolore (It.2) peut être réintroduite
*sur la base chaude* de cette itération (crème + slab-serif) sans perdre
l'équilibre trouvé ici — hypothèse non testée : combiner "une couleur de
fond chaude et un slab-serif artisanal" avec "une couleur d'identité par
pièce" plutôt que de devoir choisir entre les deux.
