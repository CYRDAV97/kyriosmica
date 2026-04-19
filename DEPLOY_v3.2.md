# DEPLOY kyriosMICA Site v3.2

**Date :** 18 avril 2026
**Cible :** `github.com/CYRDAV97/kyriosmica-site` → déploiement Vercel automatique
**Archive :** `kyriosmica-site_v3.2.zip`

---

## 1. Accès administration

**Mot de passe à retenir :**

```
kMica-2026-TqimDavoh-Benin-77
```

Longueur : 29 caractères · Hash dans le source : `90ff50fc`

**À faire immédiatement après réception :**
1. Copier le mot de passe ci-dessus
2. L'enregistrer dans un gestionnaire de mots de passe (1Password, Bitwarden, KeePass…)
3. **Ne pas** le stocker en clair dans un fichier texte ni l'envoyer par email non chiffré
4. **Ne pas** le commiter dans git

Pour changer le mot de passe ultérieurement, utiliser le panneau Administration lui-même (onglet « Sécurité » → « Changer le mot de passe »).

---

## 2. Upload GitHub via interface web (procédure rapide)

### Préparation
1. Se connecter à [github.com/CYRDAV97/kyriosmica-site](https://github.com/CYRDAV97/kyriosmica-site)
2. Télécharger `kyriosmica-site_v3.2.zip` en local
3. Décompresser l'archive dans un dossier temporaire

### Upload multi-fichiers

**Option A — Upload dossier par dossier** (recommandé pour éviter les timeouts) :

1. Dans GitHub, cliquer **« Add file » → « Upload files »**
2. Supprimer d'abord les fichiers actuels qui vont être remplacés :
   - `index.html`
   - `assets/shared/nav.js`
   - `assets/shared/nav.css`
   - `assets/shared/footer.js`
   - `CHANGELOG.md`
3. Glisser-déposer dans l'interface :
   - `index.html` (la racine)
4. Commit message : `v3.2 — Refonte scientifique TQIM-Davoh + nettoyage critique`
5. Commit directement sur `main`

**Puis répéter** pour les fichiers `assets/shared/` :
6. Nouveau « Upload files »
7. Glisser `assets/shared/nav.js`, `nav.css`, `footer.js`
8. Commit message : `v3.2 — Nav + footer enrichis : Applications / Validation / Vision`

**Puis** pour la documentation :
9. Upload `CHANGELOG_v3.2.md` et `DEPLOY_v3.2.md`
10. Commit message : `v3.2 — Documentation release`

### Option B — Git CLI (si installé)

```bash
git clone https://github.com/CYRDAV97/kyriosmica-site.git
cd kyriosmica-site
# Décompresser le zip dans ce dossier, écraser les fichiers existants
unzip -o ../kyriosmica-site_v3.2.zip

git add -A
git commit -m "v3.2 — Refonte scientifique TQIM-Davoh + nettoyage critique

- Footer legacy supprimé (double footer résolu)
- Mot de passe admin renouvelé (hash pré-calculé)
- Mentions 'Cyrille Egnon Davoh' réduites 52 → 14
- 4 nouvelles pages SPA : science (refondue), applications, validation, vision
- 4 postulats TQIM-Davoh présentés (Indétermination, Cohérence, Résonance, Mutabilité)
- 8 applications Science 4.0 avec catégories A/B et horizons
- 4 validations scientifiques avec chiffres précis
- Vision 2031 avec objectifs chiffrés
- Galerie refondue en 5 sections (13 assets Brand Kit v3)
- Bug CSS .page animation corrigé (opacity 0 sur pages non-home)
- Nav + footer enrichis de 3 entrées"

git push origin main
```

---

## 3. Vérification Vercel (60-90 secondes après le push)

Vercel détecte automatiquement les changements GitHub et redéploie. Suivre :

1. Aller sur [vercel.com](https://vercel.com) → projet `kyriosmica-site`
2. Onglet **« Deployments »** → attendre le commit v3.2 en « Ready »
3. Ouvrir la preview URL (ou directement `kyriosmica.com` si le domaine est en prod)

---

## 4. Checklist de validation post-déploiement (5 min)

Tester sur [kyriosmica.com](https://kyriosmica.com) (desktop + mobile) :

### 4.1 Double footer résolu
- [ ] Scroller tout en bas de `kyriosmica.com` (page home)
- [ ] **Un seul bloc footer** visible : logo kyriosMICA + colonnes Laboratoires / Institut + copyright
- [ ] **Pas** de second bloc « NAVIGATION / INSTITUTION » au-dessus ni en dessous

### 4.2 Nav complète
- [ ] Desktop : barre de nav affiche **Science · Applications · Validation · Vision · Laboratoires▼ · Défi Mondial · Revue · Galerie · Documents · Consortium · Contact · FR/EN**
- [ ] Clic sur **« Applications »** → affichage de la page des 8 domaines
- [ ] Clic sur **« Validation »** → affichage des 4 résultats scientifiques
- [ ] Clic sur **« Vision »** → affichage Vision 2031
- [ ] Bouton **« ← Accueil »** apparaît à gauche de la nav quand on n'est pas sur home

### 4.3 Mobile
- [ ] Nav hamburger ☰ en haut à droite
- [ ] Clic hamburger → menu déroulant propre avec toutes les entrées
- [ ] Pas de scrollbar horizontale sur la home, Science, Applications, Validation, Vision, Galerie

### 4.4 Science refondue
- [ ] Titre **« TQIM-Davoh : de Qudits-36 à l'Architecture Vibratoire »**
- [ ] Épigraphe fondatrice : **« L'ADN n'est pas seulement le livre de la vie. C'est aussi sa partition vibratoire. »** (bloc terre #8B4513)
- [ ] 4 cartes M · I · C · A (décomposition de l'acronyme)
- [ ] 4 Postulats Fondateurs (Indétermination / Cohérence / Résonance / Mutabilité)
- [ ] 3 constructions EVK · ERK · MRK
- [ ] Simulateur Qudits-36 interactif fonctionnel

### 4.5 Applications
- [ ] 8 cartes Applications avec badges catégorie (A · NOW, A · DEV, A/B, A, B, B · HYPOTHÈSE)
- [ ] Pilier 4 (Économophysique & Finance) en bas

### 4.6 Validation
- [ ] 4 cartes : 4 structures PDB / NR3C1 / SARS-CoV-2 / BRCA1
- [ ] NR3C1 : mention « Collaboration Julien Boblique · SET Theory · DOI: 10.23880/izab-16000673 »
- [ ] SARS-CoV-2 : « Pré-enregistré 9 avril 2026 · p = 0.0002 »
- [ ] Bloc « Limites Assumées · Honnêteté Scientifique » (fond terre)

### 4.7 Vision 2031
- [ ] Titre « Gardienne et Coordinatrice de la TQIM-Davoh »
- [ ] Épigraphe « La vie ne calcule pas en binaire. Elle calcule avec sa propre physique. »
- [ ] 4 objectifs chiffrés : ≥ 3 publications IF ≥ 5, ≥ 2 brevets, ≥ 10 membres Consortium sur 4 continents, ≥ 5 étudiants africains Master/Doctorat
- [ ] Roadmap 3 phases (2026 / 2027-2028 / 2028-2030)

### 4.8 Galerie refondue
- [ ] 5 boutons de navigation en haut : SVG / PNG / Planche / Favicon / Animés
- [ ] **Section 1 — SVG (5 items)** : Horizontal FR, Horizontal EN, Vertical FR, Vertical EN, Icon
- [ ] **Section 2 — PNG (5 items)** : mêmes variantes en raster
- [ ] **Section 3 — Planche composite** : brand_kit_v3.png en format large
- [ ] **Section 4 — Favicon & App Icon** : favicon.svg et favicon.ico
- [ ] **Section 5 — Animés à venir** : 3 placeholders avec cas d'usage

### 4.9 Réduction nom fondateur
- [ ] Copyright bar en bas : **« © 2026 kyriosMICA · Tous droits réservés »** (sans « Cyrille Egnon DAVOH »)
- [ ] Footer shared : **« Fondateur : Cyrille Egnon Davoh »** (une seule mention en bas)
- [ ] Page Contact : nom présent sur la carte Auteur + réseaux sociaux (total 2 mentions)
- [ ] Article meta de la revue : **« kyriosMICA »** (sans nom)
- [ ] Section galerie : **« BRAND KIT V3 »** (sans « DESIGN CYRILLE EGNON DAVOH »)

### 4.10 Accès administration
- [ ] Scroll tout en bas → bouton discret « ⚙ Administration » en gris très clair
- [ ] Clic → prompt de mot de passe
- [ ] Saisir `kMica-2026-TqimDavoh-Benin-77`
- [ ] Accès au panneau admin

---

## 5. Rollback vers v3.1 (procédure d'urgence)

Si un bug critique apparaît en production :

### Via GitHub web
1. Aller dans `kyriosmica-site` → onglet « Commits »
2. Trouver le commit v3.1 précédent
3. Cliquer le commit → onglet « Browse files »
4. Cliquer **« ... »** → **« Revert »** sur chaque fichier modifié

### Via Git CLI
```bash
cd kyriosmica-site
git log --oneline | head -5  # Identifier le commit v3.1
git revert <commit-hash-v3.2>
git push origin main
```

Vercel redéploie automatiquement v3.1 dans les 60-90 secondes.

---

## 6. Prochaines étapes après déploiement v3.2

**À faire une fois v3.2 validée en prod :**

1. ⭐ **Publication bioRxiv** : le site est structurellement aligné avec la thèse TQIM-Davoh. Les 4 postulats, 8 applications, 4 validations et Vision 2031 sont accessibles via des URLs stables (`/#science`, `/#applications`, `/#validation`, `/#vision`) qui peuvent être citées dans le manuscrit
2. **lab.kyriosmica.com** : mettre à jour avec les mêmes éléments d'identité v3.2 (Next.js, dépôt séparé)
3. **api.kyriosmica.com** : mettre à jour les métadonnées FastAPI (version, description institutionnelle)
4. **Dépôt PDFs** : KMDOC001-007 + TIQMDavoh + formalism dans `/docs/`
5. **Animations WebM** : remplacer les 3 placeholders dans la galerie section 5
6. **Traductions EN** : compléter les 559 textes wrappés en v3.1 (approche symétrique A → vraie traduction)

**À surveiller pendant les 48 h post-déploiement :**

- Logs Vercel : pas d'erreur 500
- Google Search Console : sitemap à jour (pages `#science`, `#applications`, `#validation`, `#vision` indexables via ancres)
- LinkedIn : si tu publies un post, utiliser `/assets/logos/logo_horizontal_FR.png` (3000×1000) comme bannière

---

© 2026 kyriosMICA · Institut de Recherche en Bioinformatique Quantique · Bénin, Afrique de l'Ouest
