# Mise en place de l'environnement de travail

## Pourquoi utiliser Python pour la Data Science ?
Python est un langage de programmation libre de droits, populaire et utilisé dans énormément de domaines. 

Il est utilisé dans le domaine scientifique pour l’analyse de données, et plus généralement la Data Science, 
mais aussi pour développer des applications web, des jeux, des interfaces graphiques d’outils, ou encore pour faire du développement logiciel en général. 

Il propose un ensemble complet de librairies dédiées à la Data Science et donc des fonctions facilitant la manipulation de données, les analyses statistiques sur ces données et leur visualisation, notamment.

## Le projet Jupyter
Le nom de Jupyter provient des trois langages de programmation qui ont été inclus dans le projet au début, à savoir Julia, Python et R. 

Le but du projet Jupyter était de développer des outils et services pour faire de la programmation interactive avec plusieurs langages de programmation. 
À présent, Jupyter supporte plus de quarante langages de programmation, et permet de programmer de manière interactive avec ces langages, ce qui est très important pour faire de la Data Science, d’où sa popularité dans ce domaine. 

La force de Jupyter, ce sont sans conteste ses notebooks. Un notebook est un document exécutable, qui contient du code (Python, R, ou autre) qui va pouvoir être interprété et dont les résultats seront intégrés dans le document. 
Le notebook peut aussi contenir des éléments de texte comme des paragraphes de texte, des figures, des liens, des équations mathématiques, etc.

Pour travailler avec les notebooks, il est nécessaire d’avoir l’application Jupyter Notebook, qui permettra de visualiser, modifier et exécuter les notebooks à travers un navigateur web (type Firefox ou Chrome). 

Pour pouvoir commencer à faire de la Data Science avec Python, le premier outil essentiel est Jupyter Notebook, il faut donc l’installer. Nous installerons Jupyter Notebook au travers de l’application Anaconda, présentée dans la section à suivre.

## Qu’est-ce qu’Anaconda ?
Anaconda est tout simplement la distribution Python et R la plus connue et la plus utilisée en Data Science car cette plateforme est dédiée à ce domaine précisément. 
En effet, c’est une distribution libre qui contient non seulement les environnements Python et R mais aussi toutes les librairies essentielles pour pouvoir faire de la Data Science (par exemple pour Python : NumPy, Pandas, Matplotlib, pour ne citer qu’elles). 

De plus, la distribution Anaconda inclut Jupyter Notebook, RStudio et beaucoup d’autres applications essentielles à la Data Science. Nous utiliserons uniquement Jupyter Notebook et le kernel IPython sous Anaconda, mais il est bon de savoir que cette distribution inclut les deux langages de programmation les plus populaires en Data Science.

Une interface graphique a été développée pour la distribution Anaconda ; elle s’appelle Anaconda Navigator et permet en quelques clics d’installer de nouveaux packages (ou librairies), de créer de nouveaux environnements, d’accéder aux applications, etc.

## Découverte d’Anaconda Navigator
Anaconda Navigator propose différentes applications disponibles directement lors de l’ouverture de l’outil.

En plus de faciliter le lancement des applications, Anaconda Navigator facilite l’installation et la gestion des packages et environnements.

Un environnement sous Anaconda correspond à un ensemble de packages installés, avec des versions particulières. 
En effet, certains packages nécessitent des versions spécifiques d’autres packages pour pouvoir fonctionner. 
Il est alors possible de créer des environnements différents, avec des versions de packages différentes, et de choisir son environnement avant de commencer son analyse. Ce seront les versions de packages de l’environnement chargé qui seront utilisées. Par défaut, un environnement existe sous Anaconda Navigator, qui est appelé base (root).

Note : un package regroupe des modules, qui eux-mêmes regroupent des fonctions. Une fonction en Python est un bout de code permettant de faire un traitement.

<!-- ## Prise en main de Jupyter Notebook -->
