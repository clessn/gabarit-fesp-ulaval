# gabarit-fesp-ulaval

Gabarit R Markdown pour mémoires, thèses et essais conformes aux normes de la [Faculté des études supérieures et postdoctorales (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses) de l'Université Laval.

**⚠️ Ce gabarit n'est pas approuvé officiellement par l'Université Laval.** Les gabarits officiels sont disponibles auprès de la [FESP](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction).

**📘 Optimisé pour:** Science politique • **📅 Dernière mise à jour:** Novembre 2025

---

## 🚨 NOUVELLE EXIGENCE FESP (12 janvier 2026)

**À partir du 12 janvier 2026**, tous les mémoires et thèses **doivent obligatoirement inclure un avant-propos** contenant:
1. **Une déclaration sur l'utilisation de l'intelligence artificielle générative** (obligatoire pour tous)
2. **Des informations sur les articles intégrés** (si format par articles/mixte/dossier ordonné)

**📖 Documentation:** [Déclaration IA (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative) • [Règles de présentation (PDF)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)

---

## 🚀 Démarrage rapide

```bash
# 1. Cloner le repository
git clone https://github.com/clessn/gabarit-fesp-ulaval.git
cd gabarit-fesp-ulaval

# 2. Installer les dépendances R
R -e "install.packages('rmarkdown'); remotes::install_github('rstudio/bookdown'); remotes::install_github('ismayc/thesisdown')"

# 3. Configurer pour votre type de document
cp index/examples/configurations/memoire-par-articles.yml index/_bookdown.yml
# Ou: memoire-traditionnel.yml, these-par-articles.yml, these-traditionnelle.yml, essai.yml

# 4. Éditer vos métadonnées
# Ouvrir index/index.Rmd et modifier: auteur, titre, directeur, etc.

# 5. Compiler
# Dans RStudio: Ouvrir index/index.Rmd et cliquer "Knit"
# Résultat dans: _book/Memoire_PrenomNom.pdf
```

**⚠️ Prérequis:** [LaTeX](https://tug.org/mactex/) (MacTeX/MiKTeX/TeX Live) + [R](https://www.r-project.org/) + [RStudio](https://posit.co/download/rstudio-desktop/) (recommandé)

---

## 📋 Table des matières

- [Pourquoi R Markdown?](#-pourquoi-r-markdown)
- [Structure du repository](#-structure-du-repository)
- [Types de documents](#-types-de-documents)
- [Configuration](#%EF%B8%8F-configuration)
- [Utilisation](#-utilisation)
- [Ressources FESP](#-ressources-officielles-fesp)
- [FAQ](#-faq)
- [Crédits](#-crédits)

---

## 💡 Pourquoi R Markdown?

**[R Markdown](https://rmarkdown.rstudio.com/)** combine la simplicité de Markdown avec la puissance de R et LaTeX pour produire des documents scientifiques reproductibles.

**✅ Avantages:**
- Intégration native du code et des analyses (R, Python)
- Génération automatique de graphiques et tableaux
- Gestion bibliographique BibTeX
- Collaboration via Git (fichiers texte)
- Reproductibilité scientifique complète

**📚 Documentation:** [R Markdown Guide](https://rmarkdown.rstudio.com/) • [Bookdown Manual](https://bookdown.org/yihui/bookdown/) • [Cheat Sheet (PDF)](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf)

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
│   ├── configurations/          # 5 configs YAML prêtes
│   └── avant-propos/            # 2 templates avant-propos
│
├── ulaval.cls                   # 🔧 Classe LaTeX (normes FESP)
├── template.tex                 # 🔧 Template LaTeX
└── _book/                       # 📦 PDF généré (ignoré par Git)
```

---

## 🎯 Types de documents

| Type | Programme | Articles? | Config YAML | Avant-propos | Résumé max |
|------|-----------|-----------|-------------|--------------|------------|
| **Mémoire traditionnel** | Maîtrise recherche | Non | `memoire-traditionnel.yml` | IA seulement | 300 mots |
| **Mémoire par articles** | Maîtrise recherche | Oui | `memoire-par-articles.yml` | IA + articles | 300 mots |
| **Thèse traditionnelle** | Doctorat | Non | `these-traditionnelle.yml` | IA seulement | 700 mots |
| **Thèse par articles** | Doctorat | Oui | `these-par-articles.yml` | IA + articles | 700 mots |
| **Essai** | Maîtrise professionnelle | Non | `essai.yml` | IA (vérifier avec département) | ~300 mots |

**Arbre de décision complet:** Voir [section détaillée](https://github.com/clessn/gabarit-fesp-ulaval#arbre-de-décision) (ancien README ligne 232)

---

## ⚙️ Configuration

### 1. Choisir votre configuration

Copiez le fichier YAML correspondant depuis `index/examples/configurations/`:

```bash
# Exemple pour mémoire par articles (défaut actuel):
cp index/examples/configurations/memoire-par-articles.yml index/_bookdown.yml
```

### 2. Configurer vos métadonnées

Éditez `index/index.Rmd` (section YAML en haut du fichier):

```yaml
auteur: 'Votre Prénom Nom'
date: 'Mois Année'
directeur: 'Prénom Nom du directeur'
direction: 'directeur'  # ou 'directrice'
departement: 'science politique'
grade: 'M.A.'  # M.A., M.Sc., Ph.D.
diplome: 'Maîtrise'  # ou 'Doctorat'
type: 'Mémoire'  # ou 'Thèse', 'Essai'
titre: |
  | Votre titre principal
  | Votre sous-titre (optionnel)
```

### 3. Configurer l'avant-propos (OBLIGATOIRE dès jan 2026)

Copiez le template approprié:

```bash
# Format traditionnel ou essai:
cp index/examples/avant-propos/00-avant-propos-IA-seulement.Rmd index/00-avant-propos.Rmd

# Format par articles:
cp index/examples/avant-propos/00-avant-propos-IA-et-articles.Rmd index/00-avant-propos.Rmd
```

Puis éditez `index/00-avant-propos.Rmd` pour compléter votre déclaration.

### 4. Créer vos chapitres

Créez les fichiers `.Rmd` selon votre structure (listés dans `_bookdown.yml`):

```markdown
# Titre du chapitre

Votre contenu...

## Section 1.1

Texte, code R, citations...
```

---

## 📖 Utilisation

### Compiler votre document

1. **Ouvrez `index/index.Rmd`** dans RStudio (pas les chapitres individuels!)
2. **Cliquez "Knit"**
3. Le PDF apparaît dans `_book/Memoire_PrenomNom.pdf`

### Citations et bibliographie

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

- **[Règles de présentation matérielle (PDF, 17 sept 2025)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)** ⭐ Document principal
- **[Déclaration IA générative](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative)** (obligatoire dès 12 jan 2026)
- **[Gabarits officiels (Word, LaTeX)](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction)**
- [Page principale FESP](https://www.fesp.ulaval.ca/memoires-et-theses)
- [Types de thèses](https://www.fesp.ulaval.ca/en/masters-and-doctoral-theses/types-of-theses)
- [Règles pour rédaction par articles](https://www.fesp.ulaval.ca/memoires-et-theses/regles-de-presentation-pour-la-redaction-par-articles)

---

## ❓ FAQ

### Quelle est la différence entre .cls, .csl et .sty?

- **`.cls`** (LaTeX class): Structure du document (marges, en-têtes, sections). ⛔ Ne pas modifier.
- **`.csl`** (Citation Style): Style des citations (APA par défaut). ✅ Changeable ([Zotero Styles](https://www.zotero.org/styles))
- **`.sty`** (LaTeX package): Fonctionnalités additionnelles. ⛔ Ne pas modifier.

### Dois-je déclarer l'IA même si je n'en ai pas utilisé?

**Oui, à partir du 12 janvier 2026.** Vous devez déclarer explicitement que vous n'avez pas utilisé d'IA générative.

### Comment changer le style bibliographique?

1. Téléchargez le fichier `.csl` depuis [Zotero Style Repository](https://www.zotero.org/styles)
2. Placez-le dans `index/csl/`
3. Modifiez `csl: csl/votre-style.csl` dans `index/index.Rmd`

### Erreur "Lonely \item" ou "Environment CSLReferences undefined"?

Ce problème a été résolu en novembre 2025. Faites un `git pull` pour obtenir la dernière version.

### Format par articles vs traditionnel?

- **Par articles**: Chaque chapitre est un article scientifique (publié/soumis). Vous devez être premier auteur. `chapter_name: "Article "`.
- **Traditionnel**: Structure classique (intro, revue, méthodo, résultats, discussion). `chapter_name: "Chapitre "`.

### Limites des résumés?

- **Mémoire**: 300 mots max
- **Thèse**: 700 mots max
- **Essai**: Vérifier avec votre département (~300 mots)

### Comment insérer une page blanche?

⚠️ **Éviter selon les normes FESP actuelles.** Si nécessaire pour impression recto-verso:
1. Le fichier `00-blank.Rmd` existe déjà
2. Ajoutez-le dans `_bookdown.yml` à l'endroit désiré

---

## ⚠️ Avertissements

### Validation départementale

**Consultez toujours:**
- Votre directeur/directrice de recherche
- Votre département ou faculté
- La FESP pour les règles officielles

Les règles peuvent varier selon votre programme et domaine d'études.

### Mise à jour des règles

Ce gabarit est basé sur les règles en vigueur au **4 novembre 2025** (document FESP du 17 septembre 2025).

**Avant votre dépôt final**, vérifiez:
- [Page officielle FESP](https://www.fesp.ulaval.ca/memoires-et-theses)
- [Document de règles le plus récent](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf)

---

## 👥 Crédits

**Mainteneur:** Adrien Cloutier
**Contributeurs:** Maxime Blanchard, Judith Bourque
**Basé sur:** [thesisdown](https://github.com/ismayc/thesisdown) package
**Remerciements:** [CLESSN](https://github.com/clessn)

**Historique archivé:** [clessn/gabaritRmd_memoireULaval](https://github.com/clessn/gabaritRmd_memoireULaval)

---

## 📜 Licence

Mis à disposition de la communauté universitaire de l'Université Laval. Veuillez citer les contributeurs si vous réutilisez ce gabarit.

---

**Dernière mise à jour:** Novembre 2025 • **Basé sur les règles FESP du:** 17 septembre 2025
