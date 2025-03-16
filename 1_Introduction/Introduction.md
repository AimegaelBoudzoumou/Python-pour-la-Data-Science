# Introduction

## L'explosion des données
Depuis quelques années, une explosion du volume des données a commencé. À présent, nous vivons dans un monde totalement digitalisé, 
avec l’ensemble de nos appareils connectés, l’existence des médias sociaux, et la puissance d’Internet et des données libres, 
ou open data : l’analyse de ces données est à la portée de tous, à condition de savoir programmer et d’utiliser les bons outils.

Les données ouvertes, plus communément appelées Open Data, permettent d’accéder librement à un ensemble de données qu’il est possible 
d’analyser pour en tirer de nouvelles connaissances, de nouvelles stratégies ou encore de nouveaux services.

Il existe deux types de données : les données structurées sous forme de tableaux (lignes et colonnes) et les données non structurées : 
par exemple des pages web, emails, tweets, images, audio, vidéo. 

Dans ce livre, nous traiterons uniquement des données structurées : à partir de données non structurées, 
l’analyste essaiera généralement de créer des données structurées.

En effet, les tableaux représentent la structure de données la plus populaire en analyse et la plus simple à comprendre par l’Homme. 
Par exemple, à partir d’e-mails ou de tweets, il sera courant de créer un tableau contenant les fréquences d’un ensemble de mots, 
puis de travailler sur ces fréquences pour faire ressortir des tendances. C’est pour cela que ce livre ne traitera que de l’analyse de données structurées avec Python.

## L’analyse de données
Le but de l’analyse de données est de détecter des tendances à partir de données et ainsi d’en extraire de la connaissance, 
car il est alors possible de raconter une histoire, de comprendre ce qu’il se passe et quelles en sont les conséquences. 

À partir de grands jeux de données, structurés ou non, en explorant, visualisant et analysant ces données, 
il est aussi possible de recueillir des informations utiles pour résoudre un problème.

## Connaître les sources de données libres
### Kaggle
__Kaggle__ est une plateforme très connue dans le domaine de la science des données (Data Science). 
Cette plateforme propose plus de 19 000 jeux de données dans des domaines très variés. 
Ces jeux de données sont généralement bien structurés, pour pouvoir être directement analysés.

Dans ce livre, nous travaillerons beaucoup sur un jeu de données récupéré via cette plateforme, 
dont voici le lien : https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results

### Les données gouvernementales
En Open Data, le site web le plus populaire pour récupérer des données libres est le site www.data.gov : 
il s’agit des données gouvernementales des États-Unis, avec plus de 200 000 jeux de données qui vous ouvrent les portes de la connaissance, 
à condition de savoir analyser des données, bien sûr. Son équivalent français est le site : https://www.data.gouv.fr/

Une autre source de jeux de données très intéressante est le portail de données ouvertes européennes, 
disponible sur ce site : https://data.europa.eu/euodp/fr/data/. 
Ces données gouvernementales sont utilisées par les particuliers intéressés par un domaine précis, à des fins de recherches, 
mais aussi par les entreprises qui analysent ces données pour créer de nouveaux services pour leurs clients.

### Déroulement du livre
Dans ce livre, nous allons apprendre à analyser des données avec Python et les librairies dédiées à l’analyse. 
Nous verrons ensemble comment importer un jeu de données structuré pour pouvoir ensuite le nettoyer et le filtrer, 
l’explorer et le visualiser. 

Pour pouvoir faire l’ensemble de ces étapes, nous verrons en détail les librairies principales dédiées à l’analyse de données que sont NumPy, Pandas, Matplotlib et Seaborn. 

Nous apprendrons à importer des fichiers sous forme de structures Python adaptées, 
à manipuler ces structures et à les explorer pour en faire ressortir des tendances.
