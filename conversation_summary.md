# ARIS ICE TEA — "Les 4 Mondes d'Aris" — Brief Complet pour Claude Code

---

## DOSSIER DU PROJET

Le dossier `project_game` se trouve sur le **Bureau** et contient :

```
project_game/
├── background/            ← 6 fonds JPG (Gemini) — nature luxuriante
│   ├── intro.jpg          ← Jardin luxuriant, feuilles, fruits, rayons soleil
│   ├── carte.jpg          ← Parchemin + végétation
│   ├── citron.jpg         ← Verger citronniers, lumière dorée
│   ├── pomme.jpg          ← Pommiers luxuriants, vert émeraude
│   ├── peche.jpg          ← Verger pêchers, coucher de soleil orangé
│   └── fraise.jpg         ← Buissons fruits rouges, lumière rosée
├── bouteilles/            ← 4 bouteilles Aris PNG fond transparent
│   ├── citron.png
│   ├── pomme.png
│   ├── peche.png
│   └── fraise.png
├── boutons/               ← Boutons 3D glossy PNG fond transparent (Gemini)
├── éléments_décoratifs/   ← Feuilles, bulles, cadres dorés PNG transparent
├── logo/                  ← Logo Aris PNG
│   └── logo.png
└── aris_game_v8.jsx       ← Code React actuel 100% FONCTIONNEL
```

**IMPORTANT sur les formats :**
- `background/` → JPG ok (fonds plein écran, pas besoin de transparence)
- `bouteilles/`, `boutons/`, `éléments_décoratifs/`, `logo/` → DOIVENT être PNG avec fond transparent
- Si un PNG a un fond blanc, retirer avec : `convert image.png -fuzz 10% -transparent white output.png`

---

## CONTEXTE

### La Marque
Aris Ice Tea — Thé glacé tunisien, 4 variantes : Citron, Pomme, Pêche, Fruits Rouges.

### Le Jeu
4 mondes tunisiens (Cap Bon, Testour, Zaghouan, Nabeul), chacun avec un mini-jeu unique, 3 niveaux. Score final → code promo (-10%, -20%, -30%).

### État du Code (aris_game_v8.jsx — 155KB, FONCTIONNEL)
- ✅ 4 mini-jeux complets avec 3 niveaux chacun
- ✅ Jeu 1 : Collection d'ingrédients avec panel recette latéral, recette différente par niveau
- ✅ Jeu 2 : Récolte fruits avec pièges (sucre, conservateur, colorant)
- ✅ Jeu 3 : Précision (arrêter curseur dans zone cible)
- ✅ Jeu 4 : Séquence Simon avec Fraise, Cerises, Myrtille, Framboise
- ✅ Pièges avec freeze écran + message (piment, poisson, oignon)
- ✅ Pipette graduée (seuil visuel)
- ✅ Seuil 100pts pour Citron/Pomme, pas de seuil pour Pêche/Fruits Rouges
- ✅ Sons Web Audio API complets
- ✅ Timer horloge SVG dorée + tick 10 dernières secondes
- ✅ Écran échec + Recommencer
- ✅ Score reveal animé en finale (bouteilles une par une avec compteur)
- ✅ Confetti victoire
- ✅ Bouteilles flottantes en arrière-plan
- ✅ Trophée doré sur carte (remplace cadenas)
- ✅ Logo fixe haut-gauche + Volume haut-droite

---

## LES 4 MINI-JEUX (NE PAS MODIFIER LA LOGIQUE)

| # | Monde | Jeu | Timer | Spawn |
|---|-------|-----|-------|-------|
| 1 | Citron/Cap Bon | Collection ingrédients + panel recette | 45/45/30s | 1100/800/500ms |
| 2 | Pomme/Testour | Récolte fruits, éviter pièges | 45/45/30s | 1300/1000/700ms |
| 3 | Pêche/Zaghouan | Précision (curseur + zone cible) | 5/5/7 rounds | — |
| 4 | Fruits Rouges/Nabeul | Séquence Simon (4 fruits) | [3,4,5]/[4,5,6]/[5,6,7,8] | — |

---

## PALETTE DE COULEURS

### Par Saveur
| Saveur | Background | Accent | Foncé | Text |
|--------|-----------|--------|-------|------|
| Citron | #F7E44D | #E6C200 | #7A6800 | #5D4E00 |
| Pomme | #66BB6A | #388E3C | #1B5E20 | #1B3D1C |
| Pêche | #FFA726 | #F57C00 | #BF360C | #5D3200 |
| Fruits Rouges | #EF5350 | #C62828 | #7F0000 | #4A0000 |

### Globales
- Rouge Aris : #E53935
- Vert nature : #1B3D1C
- Doré premium : #DAA520
- Fond neutre : linear-gradient(135deg, #FFF9C4, #E8F5E9, #FFF3E0)

### Font : Plus Jakarta Sans (Google Fonts, 400-900)

---

## STYLE CIBLE : "Nature Luxuriante + 3D Glossy"

Inspiré du mockup "Aris Tea Match" :
- Backgrounds : photos de jardins/vergers luxuriants (générés par Gemini)
- Boutons : 3D glossy avec reflets, ombres, bordures dorées métalliques
- Cadres : dorés, style médaillon pour les bouteilles
- Décorations : feuilles de thé, bulles, rayons de soleil
- Texte : text-shadow multiple pour lisibilité sur fonds nature

---

## MODIFICATIONS DEMANDÉES (UI UNIQUEMENT)

### RÈGLE D'OR
Ne JAMAIS modifier : logique de jeu, scores, sons, timers, seuils, recettes, pièges.
Modifier UNIQUEMENT : styles, backgrounds, layouts, animations CSS.

### 1. PAGE INTRO (Priorité haute)
- Fond : `background/intro.jpg` en cover + overlay rgba(0,0,0,0.35)
- Titre "ARIS ICE TEA" avec text-shadow 3D multicouche
- Sous-titre "La Route des Saveurs" en doré #DAA520
- 4 bouteilles en losange avec cadre doré (éléments_décoratifs si dispo)
- Bouton JOUER : image boutons/ si dispo, sinon CSS gradient + border dorée + glow
- Feuilles décoratives aux coins
- Animation entrée staggered

### 2. CARTE
- Fond : `background/carte.jpg` + overlay
- Stations dans cadres dorés (médaillons)
- Chemin : feuilles vertes au lieu de points
- Trophée doré sur conquis (déjà ok)

### 3. WORLD INTRO (par saveur)
- Fond : `background/{saveur}.jpg` + overlay gradient
- Bouteille grande avec cadre doré + drop-shadow
- Bouton 3D glossy couleur du monde

### 4. PENDANT LE JEU
- Garder fond clair (lisibilité du jeu)
- Timer dans cadre doré premium
- Bande décorative en haut si possible

### 5. PAGE FINALE (Priorité haute)
- Fond festif (intro.jpg flou + overlay doré)
- Score reveal avec effets lumineux
- Code promo dans cadre "certificat" doré premium
- Boutons 3D glossy

---

## FLOW

```
INTRO → CARTE → WORLD INTRO → JEU (×3 niveaux) → LEVEL DONE →
  score ≥ seuil (ou seuil=0) → WORLD DONE → CARTE
  score < seuil → WORLD FAIL → Recommencer
  4 mondes terminés → FINALE (score reveal animé → code promo)
```

---

## CONTRAINTES TECHNIQUES

1. Fichier JSX unique, export default, **< 200KB**
2. Images fond en base64 JPEG compressées (**max 30KB chacune**). Si trop lourd → CSS gradients.
3. **PAS de SVG complexe** dans la carte (crash)
4. Transitions : `setScreen("xxx")` direct, **pas de setTimeout** pour changer d'écran
5. `useRef` guard anti-double dans chaque mini-jeu
6. `Math.min(level, 2)` partout pour protéger les index
7. `setTimeout(50ms)` avant setScreen("play") quand restart (fix bug NaN)
8. Pas de localStorage

---

## BUGS RÉSOLUS (ne pas réintroduire)

| Bug | Fix |
|-----|-----|
| NaN dans timer après restart | Math.min(level, 2) + setTimeout 50ms |
| Double score | useRef guard dn.current |
| Crash carte SVG | Carte 100% HTML/CSS |
| Fichier trop lourd | Compression < 200KB |
| Son muet | ctx.resume() + init() dans chaque méthode |
