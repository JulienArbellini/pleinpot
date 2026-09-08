# Itération 6 — "Carnet de Terrain"

## Concept

Première itération du round 2 à changer réellement de famille pour la
police d'affichage plutôt que de rester sur un serif éditorial (It.1-3)
ou un grotesque condensé (It.4) ou un slab-serif (It.5) : ici, **IBM Plex
Mono devient la police principale/display** (titres, hero, boutons) —
jusqu'ici toujours reléguée au rôle de métadonnée technique (prix,
matière, dimensions) dans toutes les itérations précédentes. Inter reste
en texte courant. Deuxième nouveauté : le fond kraft texturé (grille façon
papier millimétré, en `linear-gradient` CSS) et un système de couleur à
deux accents fonctionnels distincts — sauge (#5F6E4F) et rouge-tampon
"tag" (#A13D2C) — plutôt qu'un swatch par pièce (It.2), zéro couleur
(It.4) ou une seule couleur signature (It.5). Troisième nouveauté :
chaque photo (hero, atelier, galerie, fiche produit, modale) reçoit un
traitement "planche de spécimen naturaliste" — bordure pointillée + repères
d'angle façon marque de calage d'imprimerie — avec légende "Fig. 01, 02…".

## Ce qui a été changé

- Typo display : IBM Plex Mono remplace Fraunces / Big Shoulders Display /
  Bitter comme police des titres et boutons — Inter conserve le texte
  courant, IBM Plex Mono garde aussi son rôle de métadonnée (`key:: value`
  dans la fiche produit), donc une seule famille joue les deux rôles.
- Fond kraft (#F1ECDC) avec grille de papier millimétré en dégradé CSS,
  encre brun-noir (#2B2620), sauge (#5F6E4F) et rouge tampon (#A13D2C)
  comme duo d'accents fonctionnels (succès/nature vs. alerte/prix/marque).
- Classe `.specimen` (bordure pointillée + pseudo-éléments `::before`/
  `::after` + divs `.cornerA`/`.cornerB` en coins rouges) appliquée à
  toutes les images du site : hero, 4 photos atelier, galerie, cartes
  produit, image de la modale — légendes "Fig. 01 — Théière « Petite
  Lampe »" façon planche scientifique.
- **Correctif appliqué avant commit** : légende du hero en
  `flex justify-between` (deux blocs de texte) se chevauchait/s'écrasait
  sur mobile — passage à `flex-col sm:flex-row sm:justify-between gap-1`
  pour un empilement propre sous 640px. Vérifié par capture d'écran.
- Menu mobile testé à l'ouverture : fond kraft opaque, bordures
  pointillées, liens en `[ GALERIE ]` monospace entre crochets — aucune
  transparence résiduelle (bug déjà corrigé dès l'It.3, reconduit correctement
  ici).

## Ce qui fonctionne

- **Le changement de famille typographique le plus net des six
  itérations.** Le mono en display est un pari plus risqué que les choix
  précédents mais c'est aussi celui qui distingue le plus clairement cette
  version de toutes les autres — aucun risque de confusion avec un site
  e-commerce générique ou une boutique Instagram.
- Le motif "planche de spécimen" répond très directement à la demande de
  Clémence pour l'aspect didactique/catalogue, en le poussant plus loin
  que le registre de l'Itération 3 : chaque photo devient un objet
  documenté plutôt qu'une simple illustration.
- Duo sauge/rouge est chaleureux et évoque le terrain, le carnet de
  croquis, l'herbier — un univers "atelier/nature" cohérent avec le
  vélo/les plantes de Clémence, différent du "luxe" (It.2) ou de la "mode"
  (It.4) sans revenir au générique "artisanal gentil" rejeté au départ.
- Aucun ajout de police supplémentaire : IBM Plex Mono et Inter étaient
  déjà chargées dans toutes les itérations précédentes pour les
  métadonnées — meilleur profil de performance du round 2.
- Bug de légende mobile trouvé et corrigé ; menu mobile vérifié opaque ;
  aucune erreur console sur l'ensemble du parcours testé.

## Ce qui ne fonctionne pas (auto-critique sévère)

- **Risque principal : dérive vers la fiche technique / planche
  scientifique plutôt que vers l'atelier de céramique chaleureux.** Le
  monospace en grande taille pour un titre de hero peut se lire comme un
  document technique, un terminal ou une spec sheet plutôt que comme une
  voix éditoriale personnelle — c'est un risque symétrique et inverse à
  celui de l'Itération 2 ("trop luxe") : ici, le risque est "trop froid/
  scientifique" malgré la chaleur du kraft et du sauge autour. À valider
  explicitement avec Clémence, comme les risques des itérations précédentes.
- **Motif de spécimen sur-appliqué.** Répéter la bordure pointillée + les
  repères d'angle sur *toutes* les images (hero, 4 photos atelier, chaque
  carte produit, chaque vignette de galerie, la modale) transforme un
  geste éditorial fort en tic visuel répétitif — le risque n'est pas
  "décoratif façon brutal" (interdit explicitement) mais "systématique au
  point de perdre son effet de surprise". Une version suivante devrait
  réserver ce traitement à un sous-ensemble d'images (ex. les 3 pièces
  phares) plutôt qu'à l'intégralité du site.
- Le fond à grille millimétrée, bien que subtil, ajoute une texture
  derrière chaque photo — légère perte de netteté perçue par rapport aux
  fonds unis des Itérations 1, 2, 3 et 5, sans toutefois retomber au
  niveau de recul de l'Itération 3 sur ce critère.
- Aucune nouveauté testée côté structure de galerie ou de boutique par
  rapport aux itérations précédentes (grille classique reprise) — la
  différenciation de cette itération repose entièrement sur la typo, la
  couleur et le motif spécimen, pas sur l'architecture de page.

## Score détaillé (sur 10, exigeant)

| Critère | Score | Justification courte |
|---|---|---|
| Direction artistique | 8 | Le changement de police display le plus net des six, mais risque réel de "fiche technique" |
| Qualité typographique | 7 | Pari audacieux, fonctionne bien en taille moyenne, plus incertain à l'échelle du hero |
| Photographie / mise en valeur | 7 | Cadrage "spécimen" valorisant, mais fond texturé et bordures ajoutent du bruit visuel |
| UX | 8 | Bug trouvé et corrigé, menu mobile vérifié opaque, fonctionnalités intactes |
| Interactivité | 7 | Même socle fonctionnel que les itérations précédentes, rien de nouveau sur cet axe |
| Caractère artistique | 8 | Identité "carnet de terrain" très distinctive, proche d'une personnalité artisanale réelle |
| Cohérence | 8 | Motif spécimen + mono + kraft tenus du header au footer |
| Mobile | 8 | Testé, bug de légende corrigé, menu confirmé opaque |
| Performance | 8 | Aucune police supplémentaire chargée — meilleur profil du round 2 |

**Moyenne : 7,7 / 10**

## Comparaison avec les versions précédentes

| Version | Score moyen /10 | Risque principal identifié |
|---|---|---|
| Itération 1 — Catalogue raisonné | 7,3 | Trop froid/générique |
| Itération 2 — Atelier Nocturne | 7,8 | "Luxe générique", pas assez "elle" |
| Itération 3 — Registre d'Atelier | 7,6 | Recul sur la photographie |
| Itération 4 — Plein Cadre | 7,6 | Dérive "marque mode" |
| Itération 5 — Signature Terracotta | 7,7 | Perte de la couleur-par-pièce ; légende masquée par défaut |
| **Itération 6 — Carnet de Terrain** | **7,7** | Dérive "fiche technique/scientifique" ; motif spécimen sur-répété |

Cette itération est la seule des six à tester un changement de police
d'affichage *et* un nouveau système de couleur *et* un nouveau motif
graphique simultanément — c'est la plus "risquée" structurellement,
avec un profil de risque inverse à celui de l'Itération 2 (froid/
scientifique plutôt que luxe). Elle confirme, comme l'Itération 5, qu'un
score moyen élevé peut coexister avec un vrai point d'interrogation
identitaire non tranché par la seule notation.

## À améliorer pour la prochaine itération

Si une septième itération devait être tentée : réserver le motif
"spécimen" aux 3 pièces phares (Petite Lampe, Soucoupe Volante, Marée
Noire) plutôt qu'à toutes les images du site, et tester une taille de
hero plus modeste pour le mono display (éviter l'effet "titre-machine à
écrire géant") — hypothèse non testée ici. Plus largement, les trois
itérations de ce round (4, 5, 6) couvrent la limite basse (3) demandée
par le brief pour ce round ; l'étape suivante logique est la synthèse
finale intégrant l'ensemble des six itérations, pas une septième
variation.
