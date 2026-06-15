# gabarit-fesp-ulaval

Gabarit R Markdown pour rédiger un mémoire, une thèse ou un essai conforme aux normes de la [Faculté des études supérieures et postdoctorales (FESP)](https://www.fesp.ulaval.ca/memoires-et-theses) de l'Université Laval. Le knit de `index/index.Rmd` produit à la fois le PDF et le fichier LaTeX (`.tex`), qu'on peut joindre au dépôt.

Ce gabarit n'est pas approuvé officiellement par l'Université Laval; les gabarits officiels sont sur le [site de la FESP](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction). Il est maintenu pour la science politique, mais sert à d'autres disciplines. Dernière mise à jour : novembre 2025 (règles FESP du 17 septembre 2025).

## Nouvelle exigence FESP (dès le 12 janvier 2026)

Tout mémoire ou thèse doit désormais comporter un **avant-propos** incluant une **déclaration sur l'usage de l'intelligence artificielle générative** (pour tous), et des **informations sur les articles intégrés** (pour les formats par articles ou mixtes). Des modèles sont fournis dans `index/examples/avant-propos/` (voir l'étape 3 du démarrage).

## Installation

1. **LaTeX** — installez une distribution complète : [MacTeX](https://tug.org/mactex/) (Mac), [MiKTeX](https://miktex.org/download) (Windows) ou `texlive-full` (Linux).
2. **R et les paquets** — installez [R](https://www.r-project.org/) et [RStudio](https://posit.co/download/rstudio-desktop/), puis :

```r
install.packages(c("rmarkdown", "remotes"))
remotes::install_github("rstudio/bookdown")
remotes::install_github("ismayc/thesisdown")
```

## Démarrage

1. **Obtenez le gabarit** — cliquez sur **Use this template** sur GitHub (ou clonez le dépôt).
2. **Choisissez votre type de document** en copiant la configuration correspondante :

   ```bash
   cp index/examples/configurations/these-par-articles.yml index/_bookdown.yml
   ```

   | Type de document | Fichier de configuration | Résumé |
   |---|---|---|
   | Mémoire traditionnel | `memoire-traditionnel.yml` | 300 mots |
   | Mémoire par articles | `memoire-par-articles.yml` | 300 mots |
   | Thèse traditionnelle | `these-traditionnelle.yml` | 700 mots |
   | Thèse par articles | `these-par-articles.yml` | 700 mots |
   | Essai | `essai.yml` | ~300 mots (à vérifier) |

3. **Ajoutez l'avant-propos** (obligatoire dès le 12 janvier 2026) en copiant le modèle adapté à votre cas :

   ```bash
   # Format traditionnel ou essai
   cp index/examples/avant-propos/00-avant-propos-IA-seulement.Rmd index/00-avant-propos.Rmd
   # Format par articles ou mixte
   cp index/examples/avant-propos/00-avant-propos-IA-et-articles.Rmd index/00-avant-propos.Rmd
   ```

4. **Renseignez vos métadonnées** dans le bloc YAML en haut de `index/index.Rmd` (auteur, date, direction, département, grade, type, titre, résumés).
5. **Compilez** : ouvrez `index/index.Rmd` dans RStudio et cliquez **Knit**. Le PDF et le `.tex` apparaissent dans `index/_book/`.

## Structure

```
index/
├── index.Rmd          Fichier principal : métadonnées (page titre) + introduction
├── _bookdown.yml      Type de document et liste des fichiers à inclure
├── 00-*.Rmd           Résumé, abstract, avant-propos, remerciements
├── 01-*.Rmd, 02-*.Rmd Chapitres ou articles
├── 99-references.Rmd  Bibliographie
├── bib/               Références BibTeX (fichier pointé dans index.Rmd)
├── csl/               Style de citation (APA par défaut)
├── figure/            Vos images
├── examples/          Configurations et modèles d'avant-propos à copier
├── ulaval.cls         Classe LaTeX (normes FESP) — ne pas modifier
├── template.tex       Gabarit LaTeX — ne pas modifier
└── _book/             Sorties PDF/.tex (ignoré par Git)
```

On rédige dans les `.Rmd` et on gère les références dans `bib/`. On ne touche pas aux fichiers `.cls`, `.tex` et `.sty`.

## Citations

Dans le texte : `[@cle2008]`, avec page `[@cle2008, 13]`, multiples `[@a2006; @b2010]`. Les entrées vont dans le fichier `.bib` du dossier `bib/` (ou via un export automatique [Zotero](https://www.zotero.org/) + [Better BibTeX](https://retorque.re/zotero-better-bibtex/)).

## FAQ

**`.cls`, `.csl`, `.sty` — quelle différence ?** `.cls` définit la structure du document (ne pas modifier), `.csl` le style des citations (modifiable; autres styles sur [Zotero](https://www.zotero.org/styles)), `.sty` ajoute des fonctionnalités LaTeX (ne pas modifier).

**Erreur « Lonely \item » / « CSLReferences undefined » ?** Corrigée en novembre 2025 — faites un `git pull`.

**Un RProject est-il nécessaire ?** Non.

## Ressources

**Apprendre R Markdown :** [Introduction à R Markdown](https://rmarkdown.rstudio.com/) · [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/) · [Manuel Bookdown](https://bookdown.org/yihui/bookdown/) (moteur de ce gabarit).

**FESP (officiel) :** [Mémoires et thèses](https://www.fesp.ulaval.ca/memoires-et-theses) · [Règles de présentation matérielle (PDF)](https://www.fesp.ulaval.ca/system/files/public/memoires-theses/synthese_regles_de_presentation_materielle_memoire_these.pdf) · [Déclaration sur l'IA générative](https://www.fesp.ulaval.ca/memoires-et-theses/utilisation-responsable-de-lintelligence-artificielle-generative) · [Gabarits officiels](https://www.fesp.ulaval.ca/memoires-et-theses/outils-de-synthese-et-langue-de-redaction).

## Avant le dépôt

Les règles peuvent varier selon le programme. Validez toujours avec votre direction de recherche, votre département et la page officielle de la FESP avant le dépôt final.

## Crédits

Mainteneur : Adrien Cloutier. Contributeurs : Maxime Blanchard, Judith Bourque. Basé sur [thesisdown](https://github.com/ismayc/thesisdown), avec le soutien de la [CLESSN](https://github.com/clessn). Réutilisation libre dans la communauté universitaire; merci de citer les contributeurs.
