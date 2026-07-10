# Galerie Photo — Rives du Fleuve

Galerie photo responsive en CSS Grid pur (HTML/CSS), avec une image mise en avant, un overlay au survol, un système de filtres par catégorie, une lightbox et une pagination.


📁 Structure du projet

galerie.html   # Fichier unique : HTML + CSS
README.md                  # Ce document

✨ Fonctionnalités

FonctionnalitéDétailGrid 3 colonnesgrid-template-columns: repeat(3, 1fr) avec grid-auto-flow: denseImage mise en avant1ère photo en grid-column: span 2 + grid-row: span 212 photosRéparties en 4 catégoriesOverlay au hoverTitre + description en fondu, transition fluide (opacity + translateY)Responsive 3 breakpoints1 colonne (mobile), 2 colonnes (tablette), 3 colonnes (desktop)LightboxOuverture au clic, navigation précédent/suivant, fermeture au clavier (Échap)Filtres par catégoriePaysages, Événements Akiéni, Portraits & Sape, ArchitecturePagination6 images par page, avec boutons numérotésLazy loadingAttribut natif loading="lazy" sur chaque imageAccessibilitéCartes focusables au clavier, :focus-visible, alt sur chaque image, prefers-reduced-motion respecté


🎨 Structure du code

CSS — le cœur du Grid

css.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 200px;
  grid-auto-flow: dense;
  gap: 14px;
}

.card.featured {
  grid-column: span 2;
  grid-row: span 2;
}

grid-auto-flow: dense permet aux images suivantes de venir combler les espaces laissés par la carte en vedette, sans laisser de trous dans la grille.


🛠️ Personnalisation


html   <button class="filter-btn" data-filter="nouvelle-categorie">Nom affiché</button>

Palette et typographie

Toutes les couleurs sont centralisées en variables CSS en haut du fichier :

css:root {
  --ink: #0F2B26;     /* fond — vert-nuit fleuve */
  --paper: #F3EEE2;   /* texte — écru raffia */
  --gold: #C9A227;    /* accent principal */
  --coral: #C13B6B;   /* accent secondaire */
  --sage: #7FA08E;
}

♿ Accessibilité


Chaque carte est focusable au clavier (tabindex="0") et s'ouvre avec Entrée
La lightbox se ferme avec Échap et se navigue avec les flèches ← →
Un contour visible (:focus-visible) est appliqué sur les éléments interactifs
Les animations sont désactivées si l'utilisateur a activé prefers-reduced-motion
Chaque image possède un attribut alt descriptif basé sur son titre
