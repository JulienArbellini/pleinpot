# Plein Pot Studio — Charte de direction artistique

Document de travail pour l'exploration autonome de nouvelles directions
artistiques. Synthèse de l'audit du code existant, des versions V1
(brutal) / V2 (éditoriale) déployées, du contenu/images disponibles, et
du feedback direct de Clémence (la céramiste).

## 1. État des lieux du code existant (commit c19a0f8, HEAD avant exploration)

- Fichier unique `index.html` (~1160 lignes), Tailwind CDN (JIT, config inline),
  vanilla JS (pas de framework), Chart.js pour un donut chart, Lucide pour les icônes.
- Sections : header sticky → hero (photo pleine largeur + texte) → drop/countdown
  (bloc cobalt plein) → boutique (grille produits + filtres) → quiz interactif
  (2 questions → recommandation) → atelier (galerie 4 photos + 4 étapes de
  fabrication + graphique temps de fabrication) → footer.
- Palette : couleurs réellement puisées dans les photos de Clémence (fuchsia
  #ED5986, cobalt #0480FC, sauge #707771, terracotta #B23D14, moutarde #F4B740,
  fond crème #FAF8F5, quasi-noir #2D2B2A).
- Typo : Outfit (display, très gras) + Plus Jakarta Sans (texte) + Space Mono
  (badges) + **Caveat (cursive, à supprimer — cf. règles ci-dessous)**.
- Fonctionnel : panier (localStorage-less, en mémoire JS), modale produit,
  filtre catégories, recherche live, tri prix, quiz à recommandation dynamique,
  formulaire VIP (simulation), countdown JS réel.

## 2. V1 (brutal) vs V2 (éditoriale) — ce qui a été appris

**V1 brutal** (commit bc59121) : bandeau défilant "PROCHAIN DROP", cadres
noirs épais + ombres décalées sur absolument tout, badges/stickers façon BD,
sticker "Coup de Cœur" qui rebondit, compte à rebours en 4 boîtes blanches
encadrées. → **Rejetée par Clémence** : "trop BD", template e-commerce générique.

**V2 éditoriale** (commit c19a0f8, état actuel) : cadres retirés sur le
contenu, halos de couleur douce, police cursive Caveat pour des légendes
manuscrites, compte à rebours en chiffres nus. → **Préférée**, mais Clémence
identifie des restes gênants : la typo cursive ("nian nian"), encore un peu
trop "instagrammeuse mignonne" par endroits (émojis dans les boutons du quiz,
petits cœurs, le mot "chouchou").

**Conclusion : V2 est le bon point de départ, pas le point d'arrivée.** Il
faut pousser plus loin dans la direction "studio d'artiste / galerie /
publication éditoriale", pas revenir en arrière vers V1.

## 3. Inventaire du contenu et des images

7 pièces réelles photographiées par Clémence (fonds colorés saturés, lumière
dure) + 4 photos d'atelier (Clémence au tour, décor à la main, défournement
du four, premier marché). Toutes déjà dans `images/`, correctement recadrées
et compressées. **Aucune nouvelle photo à aller chercher** — le matériau est
suffisant pour un vrai travail de mise en page éditoriale/galerie.

Contenu texte à conserver tel quel (Clémence valide le fond) : les 6 fiches
produit, les 4 étapes de fabrication, les 2 questions du quiz, le principe du
drop VIP, le texte "zéro plastique".

## 4. Ce que Clémence aime (à consolider, pas à jeter)

- L'aspect **didactique** (les 4 étapes de fabrication, le graphique temps
  de cuisson) → à garder et si possible approfondir.
- Les **petites questions interactives** (le quiz) → à garder, esthétique à mûrir.
- Le **prochain drop** (countdown + VIP) → à garder.
- L'**explication de la démarche/fabrication** → à garder, cœur du site.
- Le **contenu actuel** → ne pas réécrire les textes.
- L'idée d'une **page galerie** montrant toutes les pièces/photos → à créer,
  n'existe pas encore.
- La **direction V2** plus que V1 → confirmé, on part de V2.

## 5. Ce que Clémence n'aime pas (à éliminer, sans exception)

- Aspect **"trop BD"** : contours noirs épais, ombres décalées façon comic,
  formes très arrondies façon jouet.
- Côté **"trop cute"** / **"instagrammeuse qui vend un truc mimi"** : émojis
  décoratifs, mot doux ("chouchou"), petits cœurs, stickers ronds qui rebondissent.
- **Typo cursive** (Caveat) — à supprimer intégralement, sans exception, y
  compris les légendes manuscrites qui l'utilisaient.
- Tout ce qui rend la céramique **"nian nian"** : traitement gentil/mignon
  d'objets qui sont en réalité des pièces sculpturales sérieuses.

## 6. Direction artistique cible : "Esthétique + didactique"

Évoquer : studio d'artiste, galerie contemporaine, publication éditoriale,
atelier de céramique contemporain.
Éviter absolument : boutique Instagram, marque lifestyle cute, site BD,
template e-commerce générique, univers froid/corporate.

### Règles visuelles non négociables

1. **Aucune typographie cursive.** Une seule famille display (forte, mais
   pas jouet) + une famille texte sobre. Un mono en accent éditorial
   (légendes, métadonnées) est acceptable — pas de script.
2. **Pas de couleur flashy en décoration.** Les couleurs réelles de Clémence
   (fuchsia, cobalt, terracotta, sauge, moutarde) restent utilisables mais
   comme **accents fonctionnels rares** (un lien actif, un état sélectionné),
   jamais comme aplat décoratif géant sans raison de contenu. Le fond
   dominant doit être neutre (blanc cassé / gris papier / noir).
3. **Zéro sticker, badge rond, emoji, effet cartoon.** Les métadonnées
   (catégorie, prix, disponibilité) passent par de la typographie et des
   séparateurs discrets, pas par des pastilles colorées.
4. **Zéro bordure noire épaisse ni ombre "brutal" décorative.** Une bordure
   ou une ombre n'existe que si elle sert une fonction (séparer un input
   d'un fond proche, indiquer un état actif) — jamais comme signature graphique.
5. **Ne pas tomber dans le froid/corporate.** La chaleur vient de la
   matière (photos grand format, texture du grès, couleurs réelles des
   émaux) et du ton du texte (déjà bon, à ne pas aseptiser) — pas de
   décoration superflue.
6. **La photographie est l'élément principal.** Grand format, peu ou pas de
   cadre, marges généreuses. Le texte structure, la photo raconte.
7. **Interactivité subtile, jamais gadget.** Le quiz, les filtres, le
   countdown restent, mais sans emoji ni pastille ; l'interaction se
   ressent dans la réactivité (hover, transition, focus), pas dans le
   skin ludique.
8. **Ne rien supprimer sous prétexte de simplicité visuelle.** Panier,
   quiz, countdown, filtres, modale produit : toutes les fonctionnalités
   actuelles doivent survivre à la refonte, seul l'habillage change.

### Ce qui doit être ajouté

- Une **page/section galerie** parcourable avec toutes les pièces en grand
  format (au-delà des 6 fiches produit de la boutique).
- Une mise en avant **beaucoup plus forte de la photographie** (formats
  variés, plein cadre, moins de texte qui rivalise visuellement).
- Une sensation de **portfolio / archive d'artiste** : numérotation des
  pièces, métadonnées façon cartel de musée (matière, date, dimensions),
  plutôt que fiche produit e-commerce classique.

## 7. Grille de notation (utilisée à chaque itération)

Chaque itération est notée sur 10 pour :
direction artistique · qualité typographique · photographie/mise en valeur
des pièces · UX · interactivité · caractère artistique · cohérence · mobile
· performance.

Notation exigeante : 10/10 réservé à une exécution qui satisferait un
directeur artistique de galerie sans réserve. Un score ≥8 partout est rare
et doit être justifié, pas donné par défaut.
