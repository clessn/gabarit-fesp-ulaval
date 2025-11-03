# memoire-ulaval

memoire-ulaval est un gabarit .Rmd pour mémoire de maîtrise conforme aux normes de la [Faculté des études supérieures et postdoctorales](https://www.fesp.ulaval.ca/memoires-et-theses) de l'Université Laval.

En même temps de produire un pdf, le knit du fichier `index.Rmd` produit aussi un fichier LaTeX. Ce fichier LaTeX peut être transmis en même temps que le dépôt de votre mémoire.

*NB: Ce gabarit n'est pas approuvé officiellement par l'Université Laval. Les gabarits approuvés sont disponibles auprès de la [Faculté des études supérieures et postdoctorales](https://www.fesp.ulaval.ca/memoires-et-theses).*

# Contenu

Mis à part ce ReadMe, tout se trouve dans le dossier `/index`.

## `/index`

* `_bookdown.yml` permet de renommer vos fichiers pdf et tex et d'indiquer les noms des fichiers Rmd à inclure dans le knit.

* Les fichers Rmd numérotés suivent. C'est à l'intérieur que vous rédigerez les différentes section de votre mémoire. Ce n'est pas, par contre, les fichiers que vous devez «knitter».

* Ne touchez pas à `chemarr.sty`.

* `index.Rmd` est le fichier le plus important. C'est ce fichier Rmd que vous «knitterez» pour produire votre pdf et votre tex (qui apparaitront dans `/_book`). Vous pourrez rédiger l'introduction de votre mémoire au bas de ce fichier, et inscrire vos informations pour la page titre en haut.

* `template.tex` contient le code pour produire le format de votre mémoire. Normalement, à moins de problème ou de demande de modification, vous ne devriez rien y changer.

* `ulaval.cls` contient les normes ULaval pour le mémoire. Normalement, à moins de problème ou de demande de modification (comme l'année, à la ligne 337), vous ne devriez rien y changer.

## `/_book`

* Le dossier `/_book` va être là où apparaitront vos fichiers pdf et tex après le knit.

## `/bib`

* Dans le dossier `/bib`, vous allez ajouter vos sources dans le fichier `bibfile.bib`.

## `/csl`

* Le dossier `/csl` contient le bon format pour la bibliographie.

## `/figure`

* Vous devez insérer toutes vos figures dans le dossier `/figure`.

## `/_misc`

* Le dossier `/_misc` contient un ramassis de trucs utiles, mais à ne pas toucher.

# Comment utiliser ce gabarit

1. Installer une version intégrale de LaTeX*
2. Installer les prérequis dans R

```R
install.packages("rmarkdown")

if (!require("remotes")) 
  install.packages("remotes", repos = "https://cran.rstudio.org")
remotes::install_github("rstudio/bookdown")
remotes::install_github("ismayc/thesisdown")
```

3. Dans ce repo, appuyer sur le bouton vert `Use this template` afin de créer un repository sur votre compte personnel
4. Ouvrir et *knit* le fichier `index.Rmd`
5. Terminé! Le fichier PDF s'ouvre automatiquement et le fichier .tex est également sauvegardé.

*Sur Mac: [MacTex](https://tug.org/mactex/) (oui, c'est 5 GB...!)

# FAQ

## Est-ce qu'un RProject est nécessaire pour compiler le gabarit vide?

Non.

## J'obtiens une erreur "Lonely \item" ou "Environment CSLReferences undefined" lors de la compilation

Ce problème a été résolu en novembre 2025. Assurez-vous d'utiliser la version la plus récente du template. Si vous utilisez une ancienne version, référez-vous au commit de correction de compatibilité pandoc ou créez un Issue.

## J'ai trouvé une erreur. Comment est-ce que je peux vous en informer?

Vous pouvez soumettre l'erreur ou vos suggestions dans l'onglet Issues de ce repo. Afin de faciliter la résolution de problèmes, merci d'inclure un [exemple minimal reproductible](https://reprex.tidyverse.org/articles/reprex-dos-and-donts.html).

# Crédits

* Maxime Blanchard
* Adrien Cloutier
* Judith Bourque

Ce gabarit est basé en partie sur le package [thesisdown](https://github.com/ismayc/thesisdown).

# Archive

Le repository archivé [clessn/gabaritRmd_memoireULaval](https://github.com/clessn/gabaritRmd_memoireULaval) contient l'historique de certaines modifications et défis rencontrés avec ce gabarit.
