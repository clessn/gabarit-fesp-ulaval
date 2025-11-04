# gabarit-fesp-ulaval

Gabarit R Markdown pour mémoires, thèses et essais conformes aux normes de la [Faculté des études supérieures et postdoctorales (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses) de l'Université Laval.

Ce gabarit produit simultanément un fichier PDF et un fichier LaTeX lors du knit de `index/index.Rmd`.

**⚠️ Ce gabarit n'est pas approuvé officiellement par l'Université Laval.** Les gabarits officiels sont disponibles auprès de la [FESP](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction).

**📘 Optimisé pour:** Science politique • **📅 Dernière mise à jour:** Novembre 2025

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

**Quarto** est le successeur moderne de R Markdown, développé par Posit (anciennement RStudio). Il offre plusieurs avantages:
- Support multi-langages plus robuste (R, Python, Julia, Observable)
- Meilleure gestion des outputs multiples (HTML, PDF, Word, sites web)
- Architecture plus moderne et extensible

**Cependant, ce gabarit utilise R Markdown car:**
- ✅ **Gabarit LaTeX existant et testé**: Ce template a été développé et validé avec [R Markdown](https://rmarkdown.rstudio.com/) + [bookdown](https://bookdown.org/)
- ✅ **Stabilité**: R Markdown est mature et ne changera plus (maintenance mode)
- ✅ **Compatibilité**: Tous les packages et workflows existants fonctionnent
- ✅ **Spécialisé pour LaTeX/PDF**: Pour les thèses, le format final est PDF (pas HTML ou Word)
- ⚠️ **Migration Quarto**: Nécessiterait de réécrire le template LaTeX et la configuration bookdown

**Note**: Si vous commencez un nouveau projet et prévoyez produire plusieurs formats (web, slides, etc.), considérez [Quarto](https://quarto.org/). Pour une thèse FESP en PDF uniquement, R Markdown reste un excellent choix.

**📚 Pour en savoir plus:**
- **[Bookdown: Authoring Books and Technical Documents with R Markdown](https://bookdown.org/yihui/bookdown/)** - Documentation complète de bookdown (ce gabarit l'utilise)
- **[Quarto Guide](https://quarto.org/docs/guide/)** - Pour explorer l'alternative moderne

### Cas d'usage idéaux pour ce gabarit

**✅ Parfait si vous:**
- Faites des analyses quantitatives (statistiques, modélisation, data science)
- Utilisez R, Python ou tout langage de programmation dans vos recherches
- Voulez que vos graphiques et tableaux se mettent à jour automatiquement
- Appréciez la reproductibilité scientifique
- Êtes à l'aise avec les outils en ligne de commande ou souhaitez les apprendre
- Voulez un contrôle précis sur le formatage sans les complexités de LaTeX pur

**⚠️ Considérez les alternatives officielles si:**
- Vous ne faites aucune analyse de données
- Vous préférez un environnement WYSIWYG ("ce que vous voyez est ce que vous obtenez")
- Votre discipline utilise exclusivement Word (ex: certains domaines en sciences humaines)
- Vous devez collaborer avec des personnes n'utilisant que Word

### Exemple concret: Pourquoi c'est puissant

**Avec Word/LaTeX traditionnel:**
```
1. Analyser vos données dans R/SPSS/Excel
2. Générer un graphique
3. L'exporter en image
4. L'insérer dans Word/LaTeX
5. Ajuster la taille manuellement
6. Vos données changent? → Recommencer 1-5
```

**Avec R Markdown:**
```markdown
Voici mes résultats d'analyse:

'''r
model <- lm(y ~ x, data = mes_donnees)
summary(model)
plot(model)
'''

Mes données changent? → Cliquez "Knit" → Tout se met à jour automatiquement.
```

---

## 🚨 NOUVELLE EXIGENCE FESP (12 janvier 2026)

**À partir du 12 janvier 2026**, tous les mémoires et thèses dont le dépôt initial a lieu à cette date ou après **doivent obligatoirement inclure un avant-propos** contenant:

1. **Une déclaration sur l'utilisation de l'intelligence artificielle générative** (obligatoire pour tous)
2. **Des informations sur les articles intégrés** (si format par articles/mixte/dossier ordonné)

**➡️ Consultez la section [Configuration de l'avant-propos](#configuration-de-lavant-propos) pour les templates.**

**📖 Documentation officielle:**
- [Déclaration obligatoire sur l'IA générative (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative)
- [Règles de présentation matérielle (PDF, 17 sept 2025)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)

---

## 📋 Table des matières

- [Pourquoi utiliser R Markdown?](#-pourquoi-utiliser-r-markdown-pour-votre-mémoire-ou-thèse)
- [Structure du repository](#-structure-du-repository)
- [Choisir votre type de document](#-choisir-votre-type-de-document)
- [Installation rapide](#-installation-rapide)
- [Configuration pour votre situation](#%EF%B8%8F-configuration-pour-votre-situation)
- [Utilisation](#-utilisation)
- [Configuration de l'avant-propos](#-configuration-de-lavant-propos)
- [Ressources officielles FESP](#-ressources-officielles-fesp)
- [FAQ](#-faq)
- [Crédits](#-crédits)

---

## 📁 Structure du repository

### Fichiers que vous allez modifier

Ces fichiers contiennent **VOTRE contenu** et doivent être personnalisés :

```
index/
├── index.Rmd                    # 📝 Fichier principal avec vos métadonnées
├── _bookdown.yml                # ⚙️ Configuration du type de document
├── 00-resume.Rmd                # 📄 Votre résumé en français
├── 00-abstract.Rmd              # 📄 Votre résumé en anglais
├── 00-avant-propos.Rmd          # 📄 Votre avant-propos (obligatoire dès jan 2026)
├── 00--remerciements.Rmd        # 📄 Vos remerciements
├── 01-*.Rmd, 02-*.Rmd, etc.     # 📝 Vos chapitres/articles
├── 99-references.Rmd            # 📚 Section bibliographie
├── bib/
│   └── bibfile.bib              # 📚 Vos références bibliographiques
└── figure/
    └── vos-images.*             # 🖼️ Vos figures et graphiques
```

### Fichiers de configuration (NE PAS MODIFIER sauf si vous savez ce que vous faites)

Ces fichiers définissent l'**infrastructure LaTeX** et les normes FESP :

```
index/
├── ulaval.cls                   # 🔧 Classe LaTeX ULaval (normes FESP)
├── template.tex                 # 🔧 Template LaTeX principal
├── chemarr.sty                  # 🔧 Package LaTeX (flèches chimiques)
└── csl/
    └── apa.csl                  # 🔧 Style de citation APA
```

**⚠️ IMPORTANT:** Ne modifiez ces fichiers que si :
- Vous comprenez LaTeX et les classes documentaires
- Les normes FESP ont officiellement changé
- Vous devez corriger un bug spécifique

### Dossiers de référence et exemples

Ces dossiers contiennent des **templates et exemples** à copier :

```
index/
└── examples/
    ├── configurations/          # 📋 5 configurations YAML prêtes à l'emploi
    │   ├── memoire-par-articles.yml
    │   ├── memoire-traditionnel.yml
    │   ├── these-par-articles.yml
    │   ├── these-traditionnelle.yml
    │   └── essai.yml
    └── avant-propos/            # 📋 Templates d'avant-propos
        ├── 00-avant-propos-IA-seulement.Rmd
        └── 00-avant-propos-IA-et-articles.Rmd
```

### Dossiers générés automatiquement (ignorés par Git)

Ces dossiers sont **créés automatiquement** lors de la compilation et ne doivent jamais être commités :

```
index/
├── _book/                       # 📦 Fichiers PDF et LaTeX générés
├── _bookdown_files/             # 📦 Fichiers temporaires de compilation
└── _misc/                       # 📦 Fichiers divers générés (si créé)
```

**✅ Ces dossiers sont dans `.gitignore` et seront recréés à chaque compilation.**

### Résumé : Qu'est-ce que je modifie ?

| Type de fichier | Action | Exemples |
|----------------|--------|----------|
| **Fichiers .Rmd** | ✏️ À MODIFIER | `index.Rmd`, `01-*.Rmd`, `00-resume.Rmd` |
| **_bookdown.yml** | ⚙️ À CONFIGURER | Copier depuis `examples/configurations/` |
| **bib/bibfile.bib** | ✏️ À MODIFIER | Vos références BibTeX |
| **figure/** | 📁 AJOUTER VOS IMAGES | `.png`, `.pdf`, `.jpg` |
| **Fichiers .cls, .tex, .sty** | ⛔ NE PAS TOUCHER | Infrastructure LaTeX |
| **_book/**, **_bookdown_files/** | ⛔ GÉNÉRÉ AUTO | Ignorés par Git |

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
│   │   │   ├─ Avant-propos: IA + détails articles              │
│   │   │   ├─ chapter_name: "Article "                         │
│   │   │   └─ Résumé: 300 mots max                             │
│   │   │                                                         │
│   │   └─ NON → MÉMOIRE TRADITIONNEL                           │
│   │       ├─ Config: memoire-traditionnel.yml                 │
│   │       ├─ Avant-propos: IA seulement                       │
│   │       ├─ chapter_name: "Chapitre "                        │
│   │       └─ Résumé: 300 mots max                             │
│   │                                                             │
├─ Maîtrise PROFESSIONNELLE (9 crédits) → ESSAI                 │
│   ├─ Config: essai.yml                                         │
│   ├─ Avant-propos: IA (à confirmer avec département)          │
│   ├─ chapter_name: "Chapitre "                                │
│   └─ Structure simplifiée                                      │
│                                                                 │
└─ DOCTORAT → THÈSE                                             │
    │                                                             │
    ├─ Avez-vous des articles à intégrer?                        │
    │   │                                                         │
    │   ├─ OUI → THÈSE PAR ARTICLES                             │
    │   │   ├─ Config: these-par-articles.yml                   │
    │   │   ├─ Avant-propos: IA + détails articles              │
    │   │   ├─ chapter_name: "Article "                         │
    │   │   └─ Résumé: 700 mots max                             │
    │   │                                                         │
    │   └─ NON → THÈSE TRADITIONNELLE                           │
    │       ├─ Config: these-traditionnelle.yml                 │
    │       ├─ Avant-propos: IA seulement                       │
    │       ├─ chapter_name: "Chapitre "                        │
    │       └─ Résumé: 700 mots max                             │
    │                                                             │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🚀 Installation rapide

### Workflow en 5 étapes

```
1️⃣ INSTALLER          2️⃣ CHOISIR            3️⃣ CONFIGURER
   LaTeX + R    →      Type de document  →   _bookdown.yml + index.Rmd

4️⃣ RÉDIGER            5️⃣ COMPILER
   Vos chapitres  →    Knit index.Rmd → PDF dans _book/
```

### 1. Prérequis

**LaTeX (obligatoire)**

**Sur Mac:**
Installez [MacTeX](https://tug.org/mactex/) (⚠️ fichier de 5 GB):

```bash
# Ou via Homebrew:
brew install --cask mactex
```

**Sur Windows:**
Installez [MiKTeX](https://miktex.org/download) ou [TeX Live](https://www.tug.org/texlive/windows.html):
- MiKTeX recommandé pour les débutants (installation automatique des packages manquants)
- Téléchargez l'installateur depuis [miktex.org/download](https://miktex.org/download)

**Sur Linux:**
```bash
# Ubuntu/Debian
sudo apt-get install texlive-full

# Fedora
sudo dnf install texlive-scheme-full

# Arch Linux
sudo pacman -S texlive-most
```

**Packages R (obligatoires)**

Dans R ou RStudio:

```r
# Packages de base
install.packages("rmarkdown")

# Bookdown
if (!require("remotes"))
  install.packages("remotes", repos = "https://cran.rstudio.org")
remotes::install_github("rstudio/bookdown")

# Thesisdown
remotes::install_github("ismayc/thesisdown")
```

### 2. Obtenir le gabarit

**Option A: Utiliser ce gabarit directement**

Cliquez sur le bouton vert **"Use this template"** en haut de cette page pour créer votre propre repository.

**Option B: Cloner le repository**

```bash
git clone https://github.com/clessn/gabarit-fesp-ulaval.git
cd gabarit-fesp-ulaval
```

### 3. Test initial

1. Ouvrez `index/index.Rmd` dans RStudio
2. Cliquez sur **"Knit"**
3. Le PDF et le fichier .tex apparaissent dans `_book/`

✅ **Si ça fonctionne, vous êtes prêt à configurer pour votre situation!**

---

## ⚙️ Configuration pour votre situation

### Étape 1: Identifier votre type de document

Utilisez l'[arbre de décision](#arbre-de-décision) ci-dessus pour identifier votre type.

### Étape 2: Copier la bonne configuration

Allez dans `index/examples/configurations/` et copiez le contenu du fichier YAML correspondant à votre type dans `index/_bookdown.yml`.

#### Pour un mémoire par articles (défaut actuel)

```bash
# Le fichier _bookdown.yml est déjà configuré pour ce type
# Aucun changement nécessaire
```

Le fichier contient déjà:
```yaml
chapter_name: "Article "
rmd_files: ["index.Rmd", "01-article1.Rmd", "02-article2.Rmd",
            "03-conclusion.Rmd", "99-references.Rmd"]
```

#### Pour un mémoire traditionnel

```bash
cp index/examples/configurations/memoire-traditionnel.yml index/_bookdown.yml
```

Ou copiez manuellement ce contenu dans `index/_bookdown.yml`:
```yaml
chapter_name: "Chapitre "
rmd_files: ["index.Rmd", "01-revue-litterature.Rmd", "02-methodologie.Rmd",
            "03-resultats.Rmd", "04-discussion.Rmd", "05-conclusion.Rmd",
            "99-references.Rmd"]
```

#### Pour une thèse par articles

```bash
cp index/examples/configurations/these-par-articles.yml index/_bookdown.yml
```

#### Pour une thèse traditionnelle

```bash
cp index/examples/configurations/these-traditionnelle.yml index/_bookdown.yml
```

#### Pour un essai

```bash
cp index/examples/configurations/essai.yml index/_bookdown.yml
```

### Étape 3: Configurer les métadonnées dans index.Rmd

Ouvrez `index/index.Rmd` et modifiez le YAML frontmatter:

```yaml
---
# === INFORMATIONS DE BASE ===
auteur: 'Votre Prénom Nom'
date: 'Mois Année'  # ex: Avril 2026
directeur: 'Prénom Nom du directeur'
direction: 'directeur'  # ou 'directrice'

# Si vous avez un codirecteur (optionnel):
#codirecteur: 'Prénom Nom'
#codirection: 'codirecteur'  # ou 'codirectrice'

departement: 'science politique'  # Nom complet, sans majuscule
grade: 'M.A.'  # M.A., M.Sc., Ph.D., etc.

# === TYPE DE DOCUMENT ===
# Choisissez selon votre situation:

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

# === AVANT-PROPOS (OBLIGATOIRE dès le 12 janvier 2026) ===
# Voir section suivante pour créer le fichier 00-avant-propos.Rmd
avantpropos: |
  `r if(knitr:::is_latex_output()) paste(readLines("00-avant-propos.Rmd"), collapse = '\n  ')`

# === RÉSUMÉS ===
resume: |
  `r if(knitr:::is_latex_output()) paste(readLines("00-resume.Rmd"), collapse = '\n  ')`
abstract: |
  `r if(knitr:::is_latex_output()) paste(readLines("00-abstract.Rmd"), collapse = '\n  ')`

# === REMERCIEMENTS ===
remerciements: |
  `r if(knitr:::is_latex_output()) paste(readLines("00--remerciements.Rmd"), collapse = '\n  ')`

# === LISTES (optionnel) ===
lof: true  # Liste des figures
lot: true  # Liste des tableaux

# === BIBLIOGRAPHIE ===
bibliography: bib/bibfile.bib
csl: csl/apa.csl  # Style APA, changez si nécessaire
---
```

### Étape 4: Créer vos fichiers de chapitres

Selon la configuration choisie à l'étape 2, créez les fichiers `.Rmd` correspondants dans le dossier `index/`.

**Exemple pour mémoire traditionnel:**
- `01-revue-litterature.Rmd`
- `02-methodologie.Rmd`
- `03-resultats.Rmd`
- `04-discussion.Rmd`
- `05-conclusion.Rmd`

**Exemple pour mémoire par articles:**
- `01-article1.Rmd`
- `02-article2.Rmd`
- `03-conclusion.Rmd`

**Structure de base d'un chapitre:**

```markdown
# Titre du chapitre

Votre contenu ici...

## Section 1.1

Texte...

## Section 1.2

Texte...
```

### Étape 5: Configuration de l'avant-propos

**OBLIGATOIRE à partir du 12 janvier 2026**

Choisissez le template approprié dans `index/examples/avant-propos/` et copiez-le dans `index/`:

#### Pour format traditionnel (ou essai):

```bash
cp index/examples/avant-propos/00-avant-propos-IA-seulement.Rmd index/00-avant-propos.Rmd
```

Ce template contient seulement la déclaration sur l'IA.

#### Pour format par articles (ou mixte):

```bash
cp index/examples/avant-propos/00-avant-propos-IA-et-articles.Rmd index/00-avant-propos.Rmd
```

Ce template contient la déclaration sur l'IA + les sections pour détailler chaque article.

**Ensuite, éditez `index/00-avant-propos.Rmd`** pour:
- Compléter la déclaration selon votre utilisation (ou non) de l'IA
- Si format par articles: remplir les détails de chaque article intégré

### ✅ Checklist de configuration

- [ ] `_bookdown.yml` configuré avec le bon `chapter_name` et `rmd_files`
- [ ] Métadonnées dans `index.Rmd` complétées (auteur, titre, type, etc.)
- [ ] Avant-propos créé (`00-avant-propos.Rmd`) et complété
- [ ] Résumés créés (`00-resume.Rmd` et `00-abstract.Rmd`)
- [ ] Fichiers de chapitres créés selon votre structure
- [ ] Bibliographie ajoutée dans `bib/bibfile.bib`
- [ ] Figures placées dans `figure/`

---

## 📖 Utilisation

### Compiler votre document

1. **Ouvrez `index/index.Rmd`** dans RStudio (pas les fichiers de chapitres individuels!)
2. **Cliquez sur "Knit"** ou exécutez:

```r
rmarkdown::render("index/index.Rmd")
```

3. Les fichiers générés apparaissent dans `_book/`:
   - `Memoire_PrenomNom.pdf` (ou le nom configuré dans `_bookdown.yml`)
   - `Memoire_PrenomNom.tex`

### Rédaction des chapitres

- Vous pouvez éditer les fichiers de chapitres (`01-*.Rmd`, `02-*.Rmd`, etc.) individuellement
- Pour tester un chapitre seul, vous pouvez le knitter individuellement, mais **le format final ne sera correct qu'en knittant `index.Rmd`**

### Syntaxe Markdown de base

Voici les éléments les plus utilisés dans la rédaction d'un mémoire ou d'une thèse:

```markdown
# Titre de niveau 1 (chapitre)
## Titre de niveau 2 (section)
### Titre de niveau 3 (sous-section)

**Texte en gras** ou __texte en gras__
*Texte en italique* ou _texte en italique_

- Liste à puces
- Deuxième élément
  - Sous-élément indenté

1. Liste numérotée
2. Deuxième élément
3. Troisième élément

> Citation en bloc (blockquote)
> Deuxième ligne de la citation

[Lien hypertexte](https://www.example.com)

![Légende de l'image](figure/mon-image.png)
```

**Pour aller plus loin avec R Markdown:**

```markdown
'''r
# Bloc de code R exécutable
summary(mes_donnees)
plot(x, y)
'''

Référence croisée à la Figure \@ref(fig:mon-graphique)
Référence à la Table \@ref(tab:mon-tableau)

Équation inline: $E = mc^2$

Équation en bloc:
$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$
```

**💡 Astuce**: Consultez le [R Markdown Cheat Sheet](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf) et le [Bookdown Manual](https://bookdown.org/yihui/bookdown/) pour plus d'exemples.

### Citations

Utilisez la syntaxe Pandoc dans votre texte:

```markdown
Une citation simple [@lewis2008american].

Une citation avec page [@alford2005political, 13].

Plusieurs citations [@converse2006nature; @page2010rational; @iyengar2010news].
```

Ajoutez vos références dans `bib/bibfile.bib` au format BibTeX:

```bibtex
@article{lewis2008american,
  title={The American Voter Revisited},
  author={Lewis-Beck, Michael S. and Jacoby, William G.},
  journal={Political Analysis},
  year={2008}
}
```

### Figures et tableaux

Placez toutes vos figures dans le dossier `figure/` et référencez-les:

```r
knitr::include_graphics("figure/mon-graphique.png")
```

---

## 📚 Ressources officielles FESP

**⚠️ TOUJOURS consulter les sources officielles car les règles peuvent changer.**

**Les liens ci-dessous sont à jour au 4 novembre 2025.**

### Documents essentiels

- **[Règles de présentation matérielle (PDF, 17 sept 2025)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)** ⭐ **DOCUMENT PRINCIPAL**
- **[Déclaration obligatoire sur l'IA générative](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative)** (obligatoire dès le 12 janvier 2026)
- **[Gabarits officiels FESP (Word, LaTeX)](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction)**

### Pages web FESP

- [Page principale: Mémoires et thèses](https://www.fesp.ulaval.ca/memoires-et-theses)
- [Types de thèses](https://www.fesp.ulaval.ca/en/masters-and-doctoral-theses/types-of-theses)
- [Règles de présentation](https://www.fesp.ulaval.ca/memoires-et-theses/regles-de-presentation)
- [Contenu des sections](https://www.fesp.ulaval.ca/memoires-et-theses/contenu-des-sections)
- [Règles pour rédaction par articles](https://www.fesp.ulaval.ca/memoires-et-theses/regles-de-presentation-pour-la-redaction-par-articles)
- [Avant de déposer](https://www.fesp.ulaval.ca/memoires-et-theses/avant-de-deposer)

### Guides supplémentaires

- [Trousse pour utilisation responsable de l'IA générative (PDF)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/trousse_ia_generative.pdf)
- [Aide-mémoire pour l'intégration d'articles](https://www.fesp.ulaval.ca/memoires-et-theses/regles-de-presentation-pour-la-redaction-par-articles)

---

## ❓ FAQ

### Quelle est la différence entre .cls, .csl et .sty ?

Ce sont trois types de fichiers différents qui contrôlent différents aspects du formatage :

- **`.cls` (class)** : Définit la structure globale du document LaTeX
  - Exemple : `ulaval.cls` contient les normes FESP (marges, en-têtes, sections, etc.)
  - ⛔ **NE PAS modifier** sauf si les normes FESP changent officiellement

- **`.csl` (Citation Style Language)** : Définit le style des citations bibliographiques
  - Exemple : `apa.csl` formatte les citations selon le style APA
  - ✅ **Peut être changé** pour utiliser un autre style (Chicago, MLA, etc.)
  - Téléchargez d'autres styles depuis [Zotero Style Repository](https://www.zotero.org/styles)

- **`.sty` (style package)** : Package LaTeX additionnel qui ajoute des fonctionnalités spécifiques
  - Exemple : `chemarr.sty` permet d'afficher des flèches chimiques
  - ⛔ **NE PAS modifier** (package externe)

**En résumé :** Vous pouvez changer le fichier `.csl` pour modifier le style bibliographique, mais laissez les fichiers `.cls` et `.sty` intacts.

### Est-ce qu'un RProject est nécessaire pour compiler le gabarit?

Non, ce n'est pas nécessaire.

### J'obtiens une erreur "Lonely \item" ou "Environment CSLReferences undefined"

Ce problème a été résolu en novembre 2025. Assurez-vous d'utiliser la version la plus récente du template. Si vous utilisez une ancienne version, faites un `git pull` ou téléchargez la dernière version.

### Quelle est la différence entre "par articles" et "traditionnel"?

**Format par articles:**
- Chaque chapitre est un article scientifique indépendant (publié, soumis ou à venir)
- Vous devez être premier auteur ou co-premier auteur
- Nécessite un avant-propos détaillant l'état de publication et les contributions de chacun
- `chapter_name: "Article "`

**Format traditionnel (monographie):**
- Structure classique: introduction, revue de littérature, méthodologie, résultats, discussion, conclusion
- Chapitres thématiques
- Avant-propos contient seulement la déclaration IA
- `chapter_name: "Chapitre "`

### Dois-je déclarer l'utilisation de l'IA même si je n'en ai pas utilisé?

**Oui, à partir du 12 janvier 2026.** Vous devez déclarer explicitement que vous n'avez pas utilisé d'outils d'IA générative. L'absence de cette déclaration retardera le dépôt de votre mémoire ou thèse.

### Quelles sont les limites de mots pour les résumés?

- **Mémoire:** 300 mots maximum
- **Thèse:** 700 mots maximum
- **Essai:** Vérifiez avec votre département (généralement 300 mots)

### Puis-je utiliser ce gabarit pour un essai de maîtrise professionnelle?

Oui! Utilisez la configuration `essai.yml`. Cependant, **validez avec votre département** car les exigences peuvent varier selon les programmes.

### Est-ce que je peux changer le style bibliographique?

**Oui, c'est le SEUL fichier de configuration que vous devriez modifier facilement!**

Le gabarit utilise APA par défaut (`csl/apa.csl`). Pour changer :

1. Téléchargez le fichier `.csl` de votre style depuis le [Zotero Style Repository](https://www.zotero.org/styles)
2. Placez-le dans le dossier `index/csl/`
3. Modifiez la ligne `csl:` dans `index/index.Rmd`

**Exemple pour Chicago:**
```yaml
csl: csl/chicago-author-date.csl
```

**Note:** La FESP n'impose pas de style bibliographique particulier, mais vérifiez avec votre département les conventions de votre discipline.

### Dois-je utiliser "Article" ou "Chapitre" pour nommer mes sections?

Cela dépend de votre format:
- **Format par articles:** `chapter_name: "Article "`
- **Format traditionnel ou essai:** `chapter_name: "Chapitre "`

Modifiez cette valeur dans `index/_bookdown.yml`.

### Où mettre mes figures?

Toutes les figures doivent être placées dans le dossier `/figure`. Référencez-les ensuite dans vos chapitres avec des chemins relatifs.

### Comment insérer une page blanche?

**⚠️ Attention:** Selon les règles FESP actuelles (novembre 2025), **les pages blanches sont à éviter** pour faciliter la lecture à l'écran.

Cependant, si votre département l'exige ou pour impression recto-verso :

1. Le fichier `index/00-blank.Rmd` existe déjà et contient une commande `\newpage`
2. Ajoutez-le dans votre `_bookdown.yml` à l'endroit désiré :

```yaml
rmd_files: ["index.Rmd", "01-article1.Rmd", "00-blank.Rmd",
            "02-article2.Rmd", "99-references.Rmd"]
```

**Note:** Par défaut, `00-blank.Rmd` n'est PAS inclus dans les configurations d'exemple pour respecter les recommandations FESP.

### Comment modifier la police de caractères?

Les polices acceptées par la FESP sont listées dans le document officiel. Pour LaTeX, vous pouvez utiliser:
- Computer Modern (défaut)
- Latin Modern
- Times
- Palatino
- Helvetica
- Et autres (voir document FESP)

### J'ai trouvé une erreur ou j'ai une suggestion

Soumettez un **Issue** dans l'onglet Issues de ce repository. Merci d'inclure un [exemple minimal reproductible](https://reprex.tidyverse.org/articles/reprex-dos-and-donts.html) pour faciliter la résolution.

### Ce gabarit est-il compatible avec mon département?

Ce gabarit suit les règles générales de la FESP mais est **optimisé pour la science politique**.

**⚠️ Important:** Chaque département peut avoir des exigences spécifiques. **Validez toujours avec votre directeur/directrice de recherche et votre département** avant le dépôt final.

---

## ⚠️ Avertissements importants

### Validation départementale

Les règles peuvent varier selon:
- Votre département ou faculté
- Votre programme spécifique
- Les conventions de votre domaine d'études

**Consultez toujours:**
1. Votre directeur/directrice de recherche
2. Votre département ou faculté
3. La FESP pour toute question sur les règles officielles

### Mise à jour des règles

Les règles de présentation de la FESP peuvent changer. Ce gabarit est basé sur les règles en vigueur au **4 novembre 2025** (document FESP du 17 septembre 2025).

**Avant votre dépôt final:**
- Consultez la [page officielle FESP](https://www.fesp.ulaval.ca/memoires-et-theses)
- Vérifiez le [document de règles le plus récent](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)

---

## 👥 Crédits

**Mainteneur principal:**
- **Adrien Cloutier** – Adaptation et mise à disposition pour la communauté ULaval

**Contributeurs:**
- Maxime Blanchard
- Judith Bourque

**Basé sur:**
- [thesisdown](https://github.com/ismayc/thesisdown) package

**Remerciements:**
- [Chaire de leadership en enseignement des sciences sociales numériques (CLESSN)](https://github.com/clessn)

---

## 📜 Licence

Ce projet est mis à disposition de la communauté universitaire de l'Université Laval. Veuillez citer les contributeurs si vous réutilisez ou adaptez ce gabarit.

---

## 📝 Archive

Le repository archivé [clessn/gabaritRmd_memoireULaval](https://github.com/clessn/gabaritRmd_memoireULaval) contient l'historique de certaines modifications et défis rencontrés avec ce gabarit.

---

**Dernière mise à jour:** Novembre 2025 • **Basé sur les règles FESP du:** 17 septembre 2025
