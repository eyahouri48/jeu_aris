# MAPPING IMAGES → FICHIERS PRODUCTION

## Comment migrer vers la production (qualité HD)

Dans le code JSX, chaque image est stockée en base64 compressé (qualité réduite pour le prototype).
En production, remplacez chaque `const _xxx = "data:image/..."` par un import ou une URL.

### Exemple de migration :
```jsx
// PROTOTYPE (base64 compressé — qualité réduite) :
const _citron_b = "data:image/png;base64,iVBOR..."

// PRODUCTION (qualité originale) :
import _citron_b from './aris_game_assets/bottle_lemon.png'
// ou
const _citron_b = "/assets/bottle_lemon.png"
```

---

## TABLE DE CORRESPONDANCE

| Variable dans le code | Fichier dans project_game/ | Usage |
|---|---|---|
| **BACKGROUNDS** | | |
| `_bg_intro` | `assets/background/ChatGPT Image 18 mai 2026, 07_58_49.jpg` | Fond intro, world intros, finale |
| `_bg_carte` | `assets/background/ChatGPT Image May 18, 2026, 08_11_19 AM.jpg` | Fond carte (parchemin) |
| **BOUTEILLES** | | |
| `_citron_b` | `aris_game_assets/bottle_lemon.png` | Bouteille Aris Citron |
| `_pomme_b` | `aris_game_assets/bottle_apple.png` | Bouteille Aris Pomme |
| `_peche_b` | `aris_game_assets/bottle_peach.png` | Bouteille Aris Pêche |
| `_fraise_b` | `aris_game_assets/bottle_strawberry.png` | Bouteille Aris Fruits Rouges |
| **UI** | | |
| `_logo` | `aris_game_assets/logo_aris.png` | Logo Aris |
| `_trophy` | (généré — trophée doré) | Trophée victoire |
| `_btn_play` | `assets/boutons/` (le plus grand PNG) | Bouton JOUER 3D |
| **FRUITS (jeu)** | | |
| `_citron` | `aris_game_assets/fruit_citron.png` | Citron (ingrédient) |
| `_pomme_fruit` | `aris_game_assets/fruit_pomme.png` | Pomme (ingrédient) |
| `_fraise` | `aris_game_assets/fruit_fraise.png` | Fraise (ingrédient) |
| `_glacon` | `aris_game_assets/fruit_glacon.png` | Glaçon (ingrédient) |
| `_framboise` | `aris_game_assets/fruit_framboise.png` | Framboise (séquence) |
| `_cerises` | `aris_game_assets/cerises.png` | Cerises (séquence) |
| `_myrtille` | `aris_game_assets/fruit_myrtille.png` | Myrtille (séquence) |
| `_miel` | `aris_game_assets/fruit_miel.jpg` | Miel (ingrédient) |
| `_menthe` | `aris_game_assets/fruit_menthe.jpg` | Menthe (ingrédient) |
| `_fruits_rouges` | `aris_game_assets/fruit_rouges.jpg` | Mix fruits rouges |
| **PIÈGES** | | |
| `_sucre` | `aris_game_assets/piege_sucre.jpg` | Piège sucre |
| `_conservateur` | `aris_game_assets/piege_conservateur.png` | Piège conservateur |
| `_colorant` | `aris_game_assets/piege_colorant.png` | Piège colorant |
| `_piment` | `aris_game_assets/piment_rouge.png` | Piège piment |
| `_poisson` | `aris_game_assets/poisson.png` | Piège poisson |
| `_oignon` | `aris_game_assets/oignion.png` | Piège oignon |
| **RECETTES** | | |
| `_recette_citron` | `aris_game_assets/recette_citron.png` | Photo recette citron |
| `_recette_frouges` | `aris_game_assets/recette_fruits_rouges.png` | Photo recette fruits rouges |
| `_recette_peche` | `aris_game_assets/recette_peche.png` | Photo recette pêche |
| `_recette_pomme` | `aris_game_assets/recette_pomme.png` | Photo recette pomme |
| **LIEUX** | | |
| `_nabeul` | `aris_game_assets/lieu_nabeul.jpg` | Photo Nabeul |
| `_testour` | `aris_game_assets/lieu_testour.jpg` | Photo Testour |
| `_zaghouan` | `aris_game_assets/lieu_zaghouan.jpg` | Photo Zaghouan |

---

## BACKGROUNDS NON UTILISÉS (disponibles pour production)

Ces images sont dans `assets/background/` mais non embarquées dans le prototype (trop lourdes).
En production avec des URLs, utilisez-les pour les world intros :

| Fichier | Usage recommandé |
|---|---|
| `Gemini_Generated_Image_n3i63en3i63en3i6 (1).jpg` | Fond world intro CITRON (verger citrons) |
| `ChatGPT Image May 18, 2026, 08_18_31 AM.jpg` | Fond world intro POMME (pommiers) |
| `ChatGPT Image 18 mai 2026, 07_58_55.jpg` | Fond world intro PÊCHE (pêchers) |
| `Gemini_Generated_Image_n3i63en3i63en3i6.jpg` | Fond world intro FRUITS ROUGES (baies) |
| `Gemini_Generated_Image_n3i63en3i63en3i6 (2).jpg` | Fond alternatif PÊCHE |
