# CHANGELOG kyriosMICA Site · v3.2

**Date :** 18 avril 2026
**Branch :** main
**Type :** Refonte scientifique + nettoyage critique

Cette release aligne le site sur la thèse fondatrice **TQIM-Davoh v3** (document KM-DOC-009-2026), corrige les bugs critiques remontés après pré-déploiement Vercel, et enrichit l'identité visuelle avec l'ensemble du Brand Kit v3.

---

## Phase A — Nettoyage critique

### A1. Footer legacy supprimé
Le `<footer>...</footer>` legacy du monolithe v3.0 coexistait avec le footer partagé `<div id="kyrios-footer">` introduit en v3.1. Résultat : double footer visible en mobile (constaté aux captures 1000020731.jpg et 1000020732.jpg), liens « Institution » cassés car dépendaient de `showPage()` appelée de l'intérieur de `page-home`.

- Suppression de 4 585 caractères (28 lignes) correspondant au bloc `<footer>...</footer>` + `<div class="copyright-bar">` legacy
- Conservation uniquement du footer partagé rendu par `assets/shared/footer.js`
- Bouton « Administration » déplacé du footer legacy vers le footer partagé avec styling discret (police monospace 9 px, bordure cyan au hover)
- Correction parallèle : `</div>` de fermeture de `page-home` avait disparu lors de la suppression — restauré pour que toutes les pages SPA soient sibling de `page-home` au lieu d'enfants

### A2. Mot de passe administration renouvelé
L'ancien hash `simpleHash('kyriosmica2026')` stockait le mot de passe en clair dans le source (`const ADMIN_HASH = simpleHash('kyriosmica2026')` — lisible par quiconque inspecte la page).

- Remplacement par le hash pré-calculé `'90ff50fc'`
- Le plaintext n'est **plus présent dans le source**
- **Nouveau mot de passe communiqué dans la conversation Claude** (à stocker dans un gestionnaire de mots de passe)
- Algorithme de hash inchangé (`simpleHash()` compatible avec l'existant côté client)

### A3. Réduction des mentions « Cyrille Egnon Davoh »
Inventaire avant : 52 occurrences totales (index.html 25, qudits36 17, t3net 4, science4 3, simulateur 2, donnees 1). Contradiction avec le Chapitre 1.3 de la thèse TQIM-Davoh qui affirme explicitement que kyriosMICA est « seul cadre institutionnel habilité à développer, valider et publier les travaux officiels ».

- **Règle appliquée** : kyriosMICA prime, le fondateur reste tracé 3 fois (SEO meta author, carte Contact, futur Manifeste)
- Inventaire final : 14 occurrences (index.html 3, qudits36 10 en commentaires JS invisibles, t3net 1 en commentaire)
- Copyright bars : `© 2026 kyriosMICA · Cyrille Egnon DAVOH · Tous droits réservés` → `© 2026 kyriosMICA · Tous droits réservés`
- Article meta dans la revue : `Cyrille Egnon DAVOH · kyriosMICA` → `kyriosMICA`
- Section galerie : `LOGOS OFFICIELS · DESIGN CYRILLE EGNON DAVOH` → `LOGOS OFFICIELS · BRAND KIT V3`
- Admin panel user : `Cyrille Egnon DAVOH · Super Administrateur` → `Administrateur kyriosMICA`

---

## Phase B — Alignement scientifique v3.2 (thèse TQIM-Davoh)

Lecture intégrale de **4 sources fondatrices** :
- `description_tqim_davoh_v3_final.md` (814 lignes, document technique définitif)
- `TIQMDavoh.pdf` (73 pages LaTeX, thèse fondatrice, 13 chapitres / 7 parties)
- `codex_MICA_kernel.docx` (Codex stratégique : 4 piliers + 21 Q/R + spin-off finance)
- `kyriosMICAQudits36_formalism.pdf` (13 pages, article pré-publication)

**Rapport de compréhension** consolidé dans `RAPPORT_COMPREHENSION_v3.2.md` (document séparé livré en out).

### B1. Page `#science` refondue
Quatre sous-sections dans l'ordre pédagogique :
1. **Hero** avec épigraphe fondatrice « L'ADN n'est pas seulement le livre de la vie. C'est aussi sa partition vibratoire. » (mise en exergue dans un bloc terre #8B4513)
2. **Alphabet T₃ = {−1, 0, +1}** avec les cartes AT (T₃², 9 états, bascule) et CG (T₃³, 27 états, pivot) conservées, complétées des probabilités à 310 K / pH 7,4 / I 150 mM
3. **Décodage MICA lettre par lettre** en 4 cartes visuelles (M = Matrice/MRK, I = Intrication 4 niveaux, C = Coordonnée, A = Amplitudes) + traduction kyrios = κύριος = « L'Opérateur Souverain de la Matrice d'Information Quantique de l'ADN »
4. **Les 4 Postulats Fondateurs** en 4 cartes colorées avec leurs formules clés (Indétermination, Cohérence MIH-21, Résonance, Mutabilité)
5. **Les 3 constructions kyriosmica** (EVK / ERK / MRK) avec signification physique des invariants
6. Simulateur Qudits-36 interactif préservé
7. CTA vers `#applications` / `#validation` / `#vision`

### B2. Nouvelle page `#applications`
Les **8 applications Science 4.0** (Chapitre 9 de la thèse) avec catégories de maturité et horizons chiffrés :

| # | Application | Catégorie | Horizon |
|---|---|---|---|
| ① | MICA-OTP — Cryptographie post-quantique | A · NOW | Prototype 2027-2028, déploiement 2030+ |
| ② | T₃-Net — IA ternaire native | A · DEV | v3.0 sur PDB réels 2026-2027 |
| ③ | Module MPC — Virologie computationnelle | A/B | Validation GISAID 2027, opérationnel 2029 |
| ④ | Oncologie prédictive | A/B | Validation ClinVar 2027-2028 |
| ⑤ | Résistance antibiotiques | A | Prototype 2028-2030 |
| ⑥ | Module SDE — Biologie synthétique & stockage | B | 2030+ |
| ⑦ | Module MCS — Quantum docking pharmaco | B | 2028-2030 |
| ⑧ | Résonance vibratoire thérapeutique | B · HYPOTHÈSE | 2028-2032 |

Plus bloc **Pilier 4 spin-off** : économophysique et finance quantitative (MPS sur marchés financiers, bootstrapping Crypto/Forex XAUUSD avant FPGA co-location).

### B3. Nouvelle page `#validation`
Les **4 résultats scientifiques** officiels, chacun avec ses chiffres précis :

| Validation | Résultat clé | Référence |
|---|---|---|
| 4 structures PDB | ΔRang B→A = 2.3, Δ‖M‖F = 0.757 kcal/mol | 4EWZ, 3I40, 1MSI, 1D65 |
| NR3C1 (Glucocorticoid) | 777 codons, ΔRang stress pH 6.8 = +2.0 uniforme | NM_000176.3 · Boblique SET Theory DOI: 10.23880/izab-16000673 |
| SARS-CoV-2 pré-enregistré | 100 % sites rang MRK = 3 mutés, Mann-Whitney p = 0.0002 | Horodatage GitHub 9 avril 2026 |
| BRCA1 | ΔRang MRK = +12, Δ‖M‖F = 3.232, ΔE_ERK = 12.0 kcal/mol | NM_007294.4 |

Bloc **« Limites Assumées · Honnêteté Scientifique »** listant les 7 FLAG_CALIBRATE Phase 1 (E_PAULI, λ_inter, ΔE_Mg, ΔE_mod, α_σ, k_prot, χ_MPS) et la Phase 2 Drude Polarisable prévue pour 2027-2028.

### B4. Nouvelle page `#vision`
**Vision 2031** institutionnelle avec :
- Mot du fondateur en exergue : « La vie ne calcule pas en binaire. Elle calcule avec sa propre physique. »
- Rôle institutionnel de kyriosMICA (extrait du Chapitre 13 de la thèse) — « seul cadre institutionnel habilité à... »
- **4 objectifs chiffrés** : ≥ 3 publications indexées (IF ≥ 5), ≥ 2 brevets, ≥ 10 membres du Consortium sur 4 continents, ≥ 5 étudiants africains Master/Doctorat
- Phrase de souveraineté scientifique africaine (Tokyo, Berlin, São Paulo)
- **Programme expérimental 2026-2030** en 3 phases :
  - Phase 1 (2026) : 500+ PDB, trimodalité, GISAID 10k+, T₃-Net v3.0
  - Phase 2 (2027-2028) : DFT B3LYP/6-311G**, MD 100 ns, Drude polarisable, MPS complet
  - Phase 3 (2028-2030) : FTIR-2D sur oligos MIH-21, neutronographie ≤ 1.0 Å, validation ClinVar
- CTA vers Consortium et Contact

### B5. Navbar et footer enrichis
- **Nav partagée** (`assets/shared/nav.js`) : ajout des entrées `#applications`, `#validation`, `#vision` entre Science et Laboratoires. Entrée Science qui pointait vers `/lab/science4.html` redirige maintenant vers `#science` SPA (cohérence totale)
- **Footer partagé** (`assets/shared/footer.js`) : colonne Institut passée de 6 à 9 entrées (ajout Applications, Validation, Vision 2031)

### B6. Bug CSS `.page` animation corrigé
L'ancienne règle `.page { animation: fadeIn .4s ease both }` appliquait l'animation à toutes les pages dès le chargement — elle était donc « consommée » avant l'activation, ce qui faisait que les pages restaient à `opacity: 0` après clic.

- `.page { animation: ... }` → `.page.active { animation: ... }`
- Ajout explicite de `opacity: 1` dans `.page.active` comme garantie
- Résultat : les 11 pages SPA s'affichent correctement (science, applications, validation, vision, challenge, revue, galerie, documents, consortium, contact, brand-kit)

---

## Phase C — Galerie enrichie

La galerie précédente (v3.1) n'exposait que **4 PNG** + 3 placeholders WebM. Le Brand Kit v3 contient **13 assets** au total. Refonte complète en **5 sections structurées** avec navigation par ancres.

### C1. Section 1 — Logos Vectoriels SVG (5 assets)
- `logo_horizontal_FR.svg` — Site, signatures email, docs, en-têtes
- `logo_horizontal_EN.svg` — Publications internationales, posters
- `logo_primary_FR.svg` — Réseaux sociaux, stories, badges
- `logo_primary_EN.svg` — Communications internationales
- `logo_icon.svg` — Avatar, profil, symbole compact

Chaque logo a son bouton de téléchargement direct et mentionne son chemin `/assets/logos/...`.

### C2. Section 2 — Logos Rasterisés PNG (5 assets)
Les mêmes 5 variantes en format PNG avec cas d'usage distincts :
- Bannières LinkedIn 3000×1000 (FR et EN)
- Logos verticaux pour posts Instagram/stories
- Icône 1000×1000 pour app icons

### C3. Section 3 — Planche Composite Officielle
- `brand_kit_v3.png` (1600×1900, 297 KB) — Toutes les variantes en une page
- Usage : dossiers de presse, propositions aux partenaires, références de design

### C4. Section 4 — Favicon & Icône d'Application
- `favicon.svg` — Format vectoriel moderne pour onglets navigateur
- `favicon.ico` — Compatibilité anciens navigateurs, multi-résolution

### C5. Section 5 — Logos Animés (À Venir)
Trois placeholders avec cas d'usage précis :
- Animation **Web/Homepage** — révélation du logo avec accent sur « MICA »
- Animation **LinkedIn/Posts** — format carré 1:1, pulsation subtile
- Animation **Sceau/Signature** — apparition du sceau de Salomon en trace lumineuse

---

## Validations effectuées

### Test automatisé Playwright
- **11 pages SPA × 1 breakpoint desktop** : toutes opacity ≥ 0,9 et height > 1000 px (vs. home à 4107 px)
- **1 breakpoint mobile 375 px** : 0 overflow horizontal
- **0 erreur JavaScript** console sur les 4 nouvelles pages
- Nav shared : 14 items détectés (Accueil + 11 pages + FR/EN)
- Footer shared : 14 liens (Laboratoires 5 + Institut 9)

### Captures de validation
- Home desktop avec nav complète 14 items
- Page Science refondue (épigraphe + alphabet T₃)
- Page Applications (8 cartes + pilier 4)
- Page Validation (4 résultats + limites assumées)
- Page Vision 2031 (épigraphe + 4 objectifs chiffrés + 3 phases roadmap)
- Galerie sections 1-4 (SVG, PNG, composite, favicon)
- Mobile 375 px (home + science)

---

## Fichiers modifiés

```
index.html                            295 KB (+38 KB vs v3.1)
assets/shared/nav.js                  10.3 KB (+1.2 KB · 3 entrées nav)
assets/shared/footer.js               4.2 KB (+0.8 KB · 3 entrées footer + bouton admin)
assets/shared/nav.css                 14.1 KB (+0.6 KB · .kmica-admin-btn + .kmica-footer-admin)
```

Aucun nouveau fichier créé. Aucun asset supprimé. Tous les 13 assets du Brand Kit v3 désormais exposés.

---

## Prochaines étapes (hors scope v3.2)

1. **Upload sur GitHub** (`CYRDAV97/kyriosmica-site`) selon `DEPLOY_v3.2.md`
2. **lab.kyriosmica.com** (Next.js, dépôt séparé) : mise à jour identité v3.2
3. **api.kyriosmica.com** (FastAPI, dépôt séparé) : mise à jour métadonnées v3.2
4. **Publication bioRxiv TQIM-Davoh** : le site est maintenant structurellement prêt
5. **Traductions EN manuelles** des 559 textes wrappés en approche symétrique v3.1
6. **PDFs KMDOC001-007** : dépôt manuel dans `/docs/` avec identité v3.2
7. **Animations WebM** : production et dépôt dans `/assets/logos/` (3 placeholders prêts à être remplacés)

---

## Résumé des métriques

| Métrique | v3.1 | v3.2 |
|---|---|---|
| Pages SPA | 8 | 11 (+3) |
| Mentions « Cyrille Egnon Davoh » | 52 | 14 (−73 %) |
| Assets galerie exposés | 4 | 13 |
| Sections galerie | 2 (logos + animés) | 5 (SVG/PNG/planche/favicon/animés) |
| Bugs critiques | 3 (double footer, pwd visible, liens cassés) | 0 |
| Épigraphes fondatrices | 0 | 2 |
| Postulats TQIM-Davoh présentés | 0 | 4 |
| Applications Science 4.0 présentées | 0 | 8 |
| Validations scientifiques présentées | 0 | 4 |
| Objectifs Vision 2031 | 0 | 4 chiffrés |

---

© 2026 kyriosMICA · Institut de Recherche en Bioinformatique Quantique · Bénin, Afrique de l'Ouest
