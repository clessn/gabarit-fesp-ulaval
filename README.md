# gabarit-fesp-ulaval

Gabarit R Markdown pour mémoires, thèses et essais conformes aux normes de la [Faculté des études supérieures et postdoctorales (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses) de l'Université Laval.

Ce gabarit produit simultanément un fichier PDF et un fichier LaTeX lors du knit de `index/index.Rmd`.

**⚠️ Ce gabarit n'est pas approuvé officiellement par l'Université Laval.** Les gabarits officiels sont disponibles auprès de la [FESP](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction).

**📘 Optimisé pour:** Science politique • **📅 Dernière mise à jour:** Novembre 2025

---

## 🚨 NOUVELLE EXIGENCE FESP (12 janvier 2026)

**À partir du 12 janvier 2026**, tous les mémoires et thèses **doivent obligatoirement inclure un avant-propos** contenant:
1. **Une déclaration sur l'utilisation de l'intelligence artificielle générative** (obligatoire pour tous)
2. **Des informations sur les articles intégrés** (si format par articles/mixte/dossier ordonné)

**➡️ Consultez la section [Configuration de l'avant-propos](#configuration-de-lavant-propos) pour les templates.**

**📖 Documentation officielle:**
- [Déclaration obligatoire sur l'IA générative (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative)
- [Règles de présentation matérielle (PDF, 17 sept 2025)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)

---

## 🚀 Démarrage rapide

**Pour ceux qui veulent commencer immédiatement:**

```bash
# 1. Cloner et installer
git clone https://github.com/clessn/gabarit-fesp-ulaval.git
cd gabarit-fesp-ulaval

# 2. Installer les packages R (dans R ou RStudio)
install.packages("rmarkdown")
remotes::install_github("rstudio/bookdown")
remotes::install_github("ismayc/thesisdown")

# 3. Choisir votre configuration (exemple: mémoire par articles)
cp index/examples/configurations/memoire-par-articles.yml index/_bookdown.yml

# 4. Ouvrir index/index.Rmd dans RStudio et cliquer "Knit"
# → Résultat dans _book/Memoire_PrenomNom.pdf
```

**⚠️ Prérequis:** [LaTeX](https://tug.org/mactex/) + [R](https://www.r-project.org/) + [RStudio](https://posit.co/download/rstudio-desktop/) (voir [Installation détaillée](#-installation-détaillée))

---

## 📋 Table des matières

- [Pourquoi utiliser R Markdown?](#-pourquoi-utiliser-r-markdown-pour-votre-mémoire-ou-thèse)
- [Structure du repository](#-structure-du-repository)
- [Choisir votre type de document](#-choisir-votre-type-de-document)
- [Installation détaillée](#-installation-détaillée)
- [Configuration](#%EF%B8%8F-configuration)
- [Utilisation](#-utilisation)
- [Configuration de l'avant-propos](#-configuration-de-lavant-propos)
- [Ressources officielles FESP](#-ressources-officielles-fesp)
- [FAQ](#-faq)
- [Crédits](#-crédits)

---

## 💡 Pourquoi utiliser R Markdown pour votre mémoire ou thèse?

### Qu'est-ce que R Markdown?

**[R Markdown](https://rmarkdown.rstudio.com/)** combine la simplicité de **[Markdown](https://www.markdownguide.org/)** (un langage de balisage léger pour formater du texte) avec la puissance de **R** (pour l'analyse de données et les graphiques) et de **LaTeX** (pour la mise en page professionnelle).

```
Votre texte en Markdown → R Markdown → LaTeX → PDF professionnel
                              ↓
                         Analyse + Graphiques
```

**📚 Ressources pour apprendre:**
- **[Markdown Guide](https://www.markdownguide.org/)** - Guide complet pour apprendre Markdown (10-15 min)
- **[Markdown Tutorial](https://commonmark.org/help/)** - Tutoriel interactif (5 min)
- **[R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/)** - Guide complet R Markdown (gratuit)
- **[R Markdown Cookbook](https://bookdown.org/yihui/rmarkdown-cookbook/)** - Recettes pratiques et astuces
- **[R Markdown Cheat Sheet](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf)** - Aide-mémoire PDF (2 pages)

### Avantages par rapport aux gabarits Word, LaTeX ou Quarto

| Aspect | Word | LaTeX pur | **R Markdown** | Quarto |
|--------|------|-----------|----------------|--------|
| **Facilité d'écriture** | ✅ Très facile | ❌ Courbe d'apprentissage raide | ✅ Syntaxe simple et lisible | ✅ Syntaxe simple et lisible |
| **Contrôle du formatage** | ❌ Limité, formatage instable | ✅ Contrôle total | ✅ Contrôle total via LaTeX | ✅ Contrôle total via LaTeX |
| **Intégration code/analyses** | ❌ Copier-coller manuel | ⚠️ Complexe | ✅ Intégration native R/Python | ✅ Multi-langages (R/Python/Julia/Observable) |
| **Reproductibilité** | ❌ Faible | ⚠️ Manuelle | ✅ Complète et automatique | ✅ Complète et automatique |
| **Gestion bibliographie** | ⚠️ Zotero/Mendeley | ✅ BibTeX natif | ✅ BibTeX natif | ✅ BibTeX natif |
| **Figures et tableaux** | ❌ Insertion manuelle | ⚠️ Complexe | ✅ Générés automatiquement | ✅ Générés automatiquement |
| **Collaboration Git** | ❌ Difficile (binaire) | ✅ Excellent | ✅ Excellent (texte brut) | ✅ Excellent (texte brut) |
| **Maintenance à long terme** | ❌ Risque de corruption | ✅ Stable | ✅ Stable | ✅ Stable |
| **Outputs multiples** | ❌ Word seulement | ❌ PDF seulement | ⚠️ PDF/HTML/Word (limité) | ✅ PDF/HTML/Word/etc. (natif) |
| **Gabarit FESP ULaval** | ✅ Officiel | ✅ Officiel | ✅ **Ce gabarit** | ❌ Non disponible |
| **Maturité écosystème** | ✅ Très mature | ✅ Très mature | ✅ Mature et stable | ⚠️ Récent (2022), en évolution |

### Pourquoi ce gabarit utilise R Markdown plutôt que Quarto?

**[Quarto](https://quarto.org/)** est le successeur moderne de R Markdown avec support multi-langages amélioré et meilleure gestion des outputs multiples. Ce gabarit utilise R Markdown car il a été créé **avant l'existence de Quarto** (lancé en 2022) et fonctionne de manière stable pour produire des thèses conformes aux normes FESP.

**📦 Intéressé par Quarto?** Nous sommes ouverts aux contributions pour créer une version Quarto. Ouvrez une [Issue](https://github.com/clessn/gabarit-fesp-ulaval/issues) pour discuter!

**📚 Documentation:** [Bookdown Manual](https://bookdown.org/yihui/bookdown/) (utilisé par ce gabarit) • [Quarto Guide](https://quarto.org/docs/guide/)

---

## 📁 Structure du repository

```
index/
├── index.Rmd                    # 📝 Fichier principal (métadonnées + config)
├── _bookdown.yml                # ⚙️ Configuration du type de document
│
├── 00-resume.Rmd                # 📄 Résumé français
├── 00-abstract.Rmd              # 📄 Résumé anglais
├── 00-avant-propos.Rmd          # 📄 Avant-propos (OBLIGATOIRE dès jan 2026)
├── 00--remerciements.Rmd        # 📄 Remerciements
│
├── 01-*.Rmd, 02-*.Rmd, ...      # 📝 Vos chapitres/articles
├── 99-references.Rmd            # 📚 Section bibliographie
│
├── bib/bibfile.bib              # 📚 Références BibTeX
├── figure/                      # 🖼️ Vos images
│
├── examples/                    # 📋 Templates à copier
│   ├── configurations/          # 5 configurations YAML prêtes à l'emploi
│   └── avant-propos/            # 2 templates d'avant-propos
│
├── ulaval.cls                   # 🔧 Classe LaTeX (normes FESP) - NE PAS MODIFIER
├── template.tex                 # 🔧 Template LaTeX - NE PAS MODIFIER
└── _book/                       # 📦 PDF généré (ignoré par Git)
```

**Fichiers à modifier:** Les `.Rmd`, `_bookdown.yml`, et `bib/bibfile.bib`
**Fichiers à ne pas toucher:** `.cls`, `.tex`, `.sty` (infrastructure LaTeX)

---

## 🎯 Choisir votre type de document

### Arbre de décision

```
┌─ Quel est votre programme? ────────────────────────────────────┐
│                                                                 │
├─ Maîtrise RECHERCHE (24 crédits) → MÉMOIRE                    │
│   │                                                             │
│   ├─ Avez-vous des articles à intégrer?                        │
│   │   │                                                         │
│   │   ├─ OUI → MÉMOIRE PAR ARTICLES                           │
│   │   │   ├─ Config: memoire-par-articles.yml                 │
│   │   │   ├─ chapter_name: "Article "                         │
│   │   │   └─ Résumé: 300 mots max                             │
│   │   │                                                         │
│   │   └─ NON → MÉMOIRE TRADITIONNEL                           │
│   │       ├─ Config: memoire-traditionnel.yml                 │
│   │       ├─ chapter_name: "Chapitre "                        │
│   │       └─ Résumé: 300 mots max                             │
│   │                                                             │
├─ Maîtrise PROFESSIONNELLE (9 crédits) → ESSAI                 │
│   ├─ Config: essai.yml                                         │
│   └─ Résumé: ~300 mots (vérifier avec département)            │
│                                                                 │
└─ DOCTORAT → THÈSE                                             │
    │                                                             │
    ├─ Avez-vous des articles à intégrer?                        │
    │   │                                                         │
    │   ├─ OUI → THÈSE PAR ARTICLES                             │
    │   │   ├─ Config: these-par-articles.yml                   │
    │   │   ├─ chapter_name: "Article "                         │
    │   │   └─ Résumé: 700 mots max                             │
    │   │                                                         │
    │   └─ NON → THÈSE TRADITIONNELLE                           │
    │       ├─ Config: these-traditionnelle.yml                 │
    │       ├─ chapter_name: "Chapitre "                        │
    │       └─ Résumé: 700 mots max                             │
    │                                                             │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🚀 Installation détaillée

### 1. Prérequis

**LaTeX (obligatoire)**

**Mac:**
```bash
# Télécharger MacTeX (⚠️ 5 GB): https://tug.org/mactex/
# Ou via Homebrew:
brew install --cask mactex
```

**Windows:**
- Installer [MiKTeX](https://miktex.org/download) (recommandé pour débutants - installe les packages automatiquement)
- Ou [TeX Live](https://www.tug.org/texlive/windows.html)

**Linux:** Installer `texlive-full` via votre gestionnaire de packages (apt, dnf, pacman, etc.)

**Packages R (obligatoires)**

```r
# Dans R ou RStudio:
install.packages("rmarkdown")

# Bookdown
if (!require("remotes"))
  install.packages("remotes", repos = "https://cran.rstudio.org")
remotes::install_github("rstudio/bookdown")

# Thesisdown
remotes::install_github("ismayc/thesisdown")
```

### 2. Obtenir le gabarit

**Option A: Utiliser comme template GitHub**

Cliquez sur **"Use this template"** en haut de la page GitHub pour créer votre propre repository.

**Option B: Cloner**

```bash
git clone https://github.com/clessn/gabarit-fesp-ulaval.git
cd gabarit-fesp-ulaval
```

### 3. Test initial

1. Ouvrez `index/index.Rmd` dans RStudio
2. Cliquez sur **"Knit"**
3. Le PDF apparaît dans `_book/`

✅ **Si ça fonctionne, passez à la configuration!**

---

## ⚙️ Configuration

### Étape 1: Choisir votre configuration

Copiez le fichier YAML approprié depuis `index/examples/configurations/`:

```bash
# Mémoire par articles (défaut actuel - déjà configuré)
cp index/examples/configurations/memoire-par-articles.yml index/_bookdown.yml

# Mémoire traditionnel
cp index/examples/configurations/memoire-traditionnel.yml index/_bookdown.yml

# Thèse par articles
cp index/examples/configurations/these-par-articles.yml index/_bookdown.yml

# Thèse traditionnelle
cp index/examples/configurations/these-traditionnelle.yml index/_bookdown.yml

# Essai
cp index/examples/configurations/essai.yml index/_bookdown.yml
```

### Étape 2: Configurer vos métadonnées

Ouvrez `index/index.Rmd` et modifiez le YAML frontmatter:

```yaml
---
# === INFORMATIONS DE BASE ===
auteur: 'Votre Prénom Nom'
date: 'Mois Année'  # ex: Avril 2026
directeur: 'Prénom Nom du directeur'
direction: 'directeur'  # ou 'directrice'

# Si codirecteur (optionnel):
#codirecteur: 'Prénom Nom'
#codirection: 'codirecteur'  # ou 'codirectrice'

departement: 'science politique'  # Nom complet, sans majuscule
grade: 'M.A.'  # M.A., M.Sc., Ph.D., etc.

# === TYPE DE DOCUMENT ===
# Pour MÉMOIRE:
diplome: 'Maîtrise'
type: 'Mémoire'

# Pour THÈSE:
# diplome: 'Doctorat'
# type: 'Thèse'

# Pour ESSAI:
# diplome: 'Maîtrise'
# type: 'Essai'

# === TITRE ===
titre: |
  | Votre titre principal
  | Votre sous-titre (optionnel)

# === RÉSUMÉS ===
resume: |
  `r if(knitr:::is_latex_output()) paste(readLines("00-resume.Rmd"), collapse = '\n  ')`
abstract: |
  `r if(knitr:::is_latex_output()) paste(readLines("00-abstract.Rmd"), collapse = '\n  ')`

# === AVANT-PROPOS (OBLIGATOIRE dès 12 jan 2026) ===
avantpropos: |
  `r if(knitr:::is_latex_output()) paste(readLines("00-avant-propos.Rmd"), collapse = '\n  ')`

# === REMERCIEMENTS ===
remerciements: |
  `r if(knitr:::is_latex_output()) paste(readLines("00--remerciements.Rmd"), collapse = '\n  ')`

# === BIBLIOGRAPHIE ===
bibliography: bib/bibfile.bib
csl: csl/apa.csl  # Style APA, changez si nécessaire
---
```

### Étape 3: Configuration de l'avant-propos

**OBLIGATOIRE à partir du 12 janvier 2026**

Choisissez le template approprié:

```bash
# Format traditionnel (ou essai):
cp index/examples/avant-propos/00-avant-propos-IA-seulement.Rmd index/00-avant-propos.Rmd

# Format par articles (ou mixte):
cp index/examples/avant-propos/00-avant-propos-IA-et-articles.Rmd index/00-avant-propos.Rmd
```

**Puis éditez `index/00-avant-propos.Rmd`** pour compléter votre déclaration selon votre utilisation (ou non) de l'IA.

### Étape 4: Créer vos chapitres

Créez les fichiers `.Rmd` listés dans votre `_bookdown.yml`:

**Structure d'un chapitre:**
```markdown
# Titre du chapitre

Votre contenu ici...

## Section 1.1

Texte...

## Section 1.2

Texte...
```

---

## 📖 Utilisation

### Compiler votre document

1. **Ouvrez `index/index.Rmd`** dans RStudio (pas les chapitres individuels!)
2. **Cliquez "Knit"**
3. Le PDF et le fichier .tex apparaissent dans `_book/`

**💡 Aide à la rédaction:** [R Markdown Cheat Sheet](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf) • [Bookdown Manual](https://bookdown.org/yihui/bookdown/)

### Citations

**Dans votre texte:**
```markdown
Citation simple [@lewis2008american].
Avec page [@alford2005political, 13].
Multiples [@converse2006nature; @page2010rational].
```

**Dans `bib/bibfile.bib`:**
```bibtex
@article{lewis2008american,
  title={The American Voter Revisited},
  author={Lewis-Beck, Michael S. and Jacoby, William G.},
  journal={Political Analysis},
  year={2008}
}
```

### Figures

```r
# Placer vos images dans figure/
knitr::include_graphics("figure/mon-graphique.png")
```

---

## 📚 Ressources officielles FESP

**⚠️ TOUJOURS consulter les sources officielles avant le dépôt final.**

**Documents essentiels:**
- **[Règles de présentation matérielle (PDF, 17 sept 2025)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)** ⭐ Document principal
- **[Déclaration obligatoire sur l'IA générative](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative)** (obligatoire dès 12 jan 2026)
- **[Gabarits officiels FESP (Word, LaTeX)](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction)**

**Pages web FESP:**
- [Page principale: Mémoires et thèses](https://www.fesp.ulaval.ca/memoires-et-theses)
- [Types de thèses](https://www.fesp.ulaval.ca/en/masters-and-doctoral-theses/types-of-theses)
- [Règles de présentation](https://www.fesp.ulaval.ca/memoires-et-theses/regles-de-presentation)
- [Règles pour rédaction par articles](https://www.fesp.ulaval.ca/memoires-et-theses/regles-de-presentation-pour-la-redaction-par-articles)

---

## ❓ FAQ

### Quelle est la différence entre .cls, .csl et .sty?

- **`.cls`** (LaTeX class): Structure du document (marges, en-têtes, sections). ⛔ **Ne pas modifier**.
- **`.csl`** (Citation Style): Style des citations (APA par défaut). ✅ **Changeable** - autres styles sur [Zotero](https://www.zotero.org/styles)
- **`.sty`** (LaTeX package): Fonctionnalités additionnelles. ⛔ **Ne pas modifier**.

### Erreur "Lonely \item" ou "Environment CSLReferences undefined"?

Ce problème a été résolu en novembre 2025. Faites `git pull` pour obtenir la dernière version.

### Comment insérer une page blanche?

Le fichier `00-blank.Rmd` existe déjà. Ajoutez-le dans `_bookdown.yml` à l'endroit désiré (déconseillé par la FESP pour faciliter lecture à l'écran).

---

## ⚠️ Avertissements

### Validation départementale

**Consultez toujours:**
- Votre directeur/directrice de recherche
- Votre département ou faculté
- La FESP pour les règles officielles

Les règles peuvent varier selon votre programme et domaine.

### Mise à jour des règles

Ce gabarit est basé sur les règles en vigueur au **4 novembre 2025** (document FESP du 17 septembre 2025).

**Avant le dépôt final:**
- Consultez la [page officielle FESP](https://www.fesp.ulaval.ca/memoires-et-theses)
- Vérifiez le [document de règles le plus récent](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)

---

## 👥 Crédits

**Mainteneur principal:** Adrien Cloutier
**Contributeurs:** Maxime Blanchard, Judith Bourque
**Basé sur:** [thesisdown](https://github.com/ismayc/thesisdown) package
**Remerciements:** [CLESSN](https://github.com/clessn)

**Historique archivé:** [clessn/gabaritRmd_memoireULaval](https://github.com/clessn/gabaritRmd_memoireULaval)

---

## 📜 Licence

Mis à disposition de la communauté universitaire de l'Université Laval. Veuillez citer les contributeurs si vous réutilisez ce gabarit.

---

**Dernière mise à jour:** Novembre 2025 • **Basé sur les règles FESP du:** 17 septembre 2025
