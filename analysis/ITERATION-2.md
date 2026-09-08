# Itération 2 — "Atelier Nocturne"

## Concept

Rupture structurelle avec l'Itération 1, pas seulement cosmétique : thème
sombre chaud (charbon #18150F, texte ivoire #EDE7DA) plutôt que le papier
clair de l'itération 1, et surtout un **système de couleur fonctionnel** —
chaque pièce porte un petit point de couleur (« swatch ») repris de sa
propre photographie, utilisé de façon cohérente dans la galerie, la
boutique, la modale et le panier comme repère d'identité visuelle, jamais
comme décoration gratuite. La grille de galerie passe d'un masonry en
colonnes (itération 1) à une grille éditoriale alternée grand/petit
(2 tailles de vignette qui zigzaguent), mécanique de layout différente.

## Ce qui a été changé

- Fond et texte inversés (sombre/clair) par rapport à l'itération 1 et à
  V1/V2 — jamais testé dans les versions précédentes.
- Nouveau champ `swatch` par produit (hex exact issu de sa photo), affiché
  en petit point partout où la pièce apparaît.
- Galerie reconstruite en grille 12 colonnes alternée (7/5, 5/7, 7/5) au
  lieu du masonry CSS de l'itération 1 — layout génériquement différent,
  pas un simple changement de couleur.
- Doughnut chart recoloré avec les couleurs swatch réelles sur fond sombre.
- Reprise des correctifs de l'itération 1 (menu mobile, `selectQuiz` sans
  `window.event` implicite, image du mug recadrée).
- **Correctif appliqué avant commit** : les filtres de catégorie et le
  bouton "Tout voir" sont passés d'un simple soulignement fin (faible
  affordance, déjà repéré comme point faible en itération 1 et non corrigé
  à l'époque) à une vraie pastille pleine pour l'état actif — plus lisible
  comme contrôle cliquable, sans revenir à un style "brutal".

## Ce qui fonctionne

- Le fond sombre change radicalement la perception des photos : les
  couleurs saturées de Clémence (lavande, bleu, fuchsia) gagnent en
  intensité dramatique — probablement la meilleure mise en valeur
  photographique des quatre versions (V1, V2, Itération 1, Itération 2).
- Le système de swatch résout directement la critique de l'itération 1
  ("perd la couleur propre à Clémence") sans jamais utiliser la couleur en
  aplat décoratif — elle reste un repère fonctionnel, cohérent avec la
  règle "éviter les couleurs flashy utilisées comme décoration".
- La grille alternée de galerie a un vrai rythme éditorial, différent du
  masonry — meilleure démonstration que "plusieurs directions" ne veut pas
  dire "plusieurs couleurs de la même page".
- Toutes les fonctionnalités (panier, filtres, recherche, tri, quiz,
  countdown, coupon, modale, menu mobile) testées et fonctionnelles, zéro
  erreur console.

## Ce qui ne fonctionne pas (auto-critique sévère)

- **Risque identitaire inverse de l'itération 1.** Un thème sombre évoque
  la galerie haut de gamme / l'objet de luxe — mais ce n'est pas
  nécessairement "elle". Sa bio Instagram ("vélo, plantes, chat", ton
  décontracté) suggère une personnalité plus légère que ce que ce noir
  élégant transmet. Le risque n'est plus "boutique Instagram mignonne" ni
  "site froid corporate", mais un troisième écueil non listé dans le
  brief : **"boutique d'objets de luxe génériques"** (un peu comme un site
  de joaillerie contemporaine). À valider directement auprès de Clémence.
- **Lisibilité du serif fin sur fond sombre non vérifiée formellement.**
  Les graisses light/regular de Fraunces peuvent créer un effet de
  vibration ("halation") sur charbon, surtout en petite taille — je n'ai
  pas testé avec un outil de contraste WCAG, seulement à l'œil.
- **La tension "countdown + urgence" n'est pas résolue par le skin.** Même
  habillé sobrement, un compte à rebours + formulaire VIP reste un
  mécanisme d'urgence commerciale ; aucune des deux itérations ne
  repense la fonctionnalité elle-même, seulement son apparence. Clémence
  a dit apprécier "le prochain drop" donc le principe est validé, mais le
  risque "hype" n'est pas nul.
- Comme en itération 1, la grille boutique garde un recadrage carré
  uniforme, moins "portfolio" que la grille de galerie juste au-dessus.

## Score détaillé (sur 10, exigeant)

| Critère | Score | Justification courte |
|---|---|---|
| Direction artistique | 8 | Distinctive et cohérente avec le brief, mais introduit un risque "luxe générique" à valider |
| Qualité typographique | 7 | Même paire que l'itération 1 ; lisibilité du serif fin sur fond sombre non vérifiée formellement |
| Photographie / mise en valeur | 9 | Meilleure mise en valeur photographique observée sur les 4 versions |
| UX | 8 | Corrigé : affordance des filtres renforcée avant commit (contrairement à l'itération 1) |
| Interactivité | 7 | Tout est préservé, sobre comme demandé, pas de régression |
| Caractère artistique | 8 | Mémorable et distinct, système de couleur fonctionnel intelligent |
| Cohérence | 8 | Système tenu sur l'ensemble du site |
| Mobile | 8 | Testé à 375px, menu mobile fonctionnel |
| Performance | 7 | Toujours Tailwind CDN, inchangé |

**Moyenne : 7,8 / 10**

## Comparaison avec V1 / V2 / Itération 1

- Score moyen supérieur à l'Itération 1 (7,8 vs 7,3), porté par la
  photographie et une UX déjà corrigée en amont du commit.
- Répond directement au point faible identifié en Itération 1 (couleur
  reléguée au seul graphique) via le système de swatch.
- Contrairement à V1 (brutal, rejeté) et V2 (mix jugé "pas terrible"),
  aucune des deux itérations ne réintroduit BD, cursive ou stickers.
- Le choix clair/sombre entre Itération 1 et 2 est la variable la plus
  importante restant à trancher **avec Clémence elle-même** — c'est un
  choix de goût autant que d'exécution, qu'aucune note chiffrée ne peut
  arbitrer seule.

## À améliorer pour une prochaine itération

Tester une version qui garde le système de swatch fonctionnel (le
meilleur apport de cette itération) mais sur un fond clair plutôt que
sombre, pour vérifier si le compromis "chaleur + rigueur éditoriale" est
atteignable sans le risque "luxe générique" du thème nocturne — ce sera
l'objet de l'itération suivante.
