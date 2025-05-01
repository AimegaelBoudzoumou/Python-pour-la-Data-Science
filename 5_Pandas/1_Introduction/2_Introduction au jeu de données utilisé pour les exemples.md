# 2. Introduction au jeu de données utilisé pour les exemples

Pour s’appuyer sur des exemples tout au long de ce chapitre, nous allons utiliser le jeu de données nommé 
_120 years of Olympic history: athletes and results_, que vous pouvez traduire par "120 ans d’histoire des jeux olympiques : athlètes et résultats". 

Ce jeu de données est disponible sur la plateforme Kaggle, à l’adresse qui suit : 
https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results

Le fichier "120-years-of-olympic-history-athletes-and-results.csv" contient des informations sur les résultats de l’ensemble des athlètes 
ayant participé aux Jeux olympiques de 1896 à 2016. 

La personne ayant créé ce jeu de données a récupéré les informations à partir du site web : www.sports-reference.com

Il s’agit d’un tableau à deux dimensions dont nous allons nous servir pour illustrer l’utilisation de la librairie Pandas 
mais aussi des librairies Matplotlib et Seaborn, dans les prochains chapitres.

Ce tableau contient 271  116 lignes, une ligne correspondant à un athlète et ses résultats à l’épreuve à laquelle il a participé. 
Un athlète peut être présent plusieurs fois dans le tableau, puisqu’il a pu participer à plusieurs épreuves et/ou à plusieurs Jeux olympiques.

Ce tableau contient 15 colonnes, dont voici la description :

-```ID``` : chaque athlète a un identifiant unique dans le tableau, rangé dans la colonne ID, 
ce qui permet de bien les différencier au cas où deux athlètes seraient des homonymes.

-```Name``` : le nom de l’athlète.

-```Sex``` : le sexe de l’athlète (F pour féminin et M pour masculin).

-```Age``` : l’âge de l’athlète.

-```Height``` : la taille de l’athlète, en centimètres.

-```Weight``` : le poids de l’athlète, en kilogrammes.

-```Team``` : le nom de l’équipe à laquelle appartient l’athlète.

-```NOC``` : NOC signifie Comités Nationaux Olympiques (CNO), qui est un code à trois lettres correspondant à un pays. 
Les CNO ont pour mission de promouvoir et protéger le mouvement olympique dans leur pays respectif.

-```Games``` : l’année et la saison des Jeux olympiques. L’année est comprise entre 1896 et 2016. 
La saison peut prendre deux valeurs, Summer (pour les JO d’été) et Winter (pour les JO d’hiver). 
Il faut savoir que jusqu’en 1992, les JO d’été et d’hiver étaient organisés la même année, 
puis il a été décidé de les organiser tous les quatre ans avec deux années de décalage. 
Ainsi, en 1994, il y a eu les JO d’hiver, puis en 1996 les JO d’été, puis en 1998 les JO d’hiver, etc. 
Donc il faut garder en tête que jusqu’en 1992, 
il est possible de trouver les Jeux olympiques d’hiver et d’été la même année dans le tableau.

-```Year``` : l’année où l’athlète a participé à l’épreuve sportive des JO.

-```Season``` : la saison des JO (été ou hiver, Summer ou Winter).

-```City``` : la ville hôte des Jeux olympiques.

-```Sport``` : le sport dont fait partie l’épreuve à laquelle l’athlète a participé.

-```Event``` : l’épreuve à laquelle l’athlète a participé. 
Par exemple, pour la natation (qui est le sport), il peut y avoir l’épreuve du 200 m brasse hommes, 
l’épreuve du 400 m brasse hommes, etc.

-```Medal``` : la médaille obtenue par l’athlète pour cette épreuve. 
Les valeurs possibles sont Gold (or), Silver (argent), Bronze (bronze) ou 
NA (NA signifie Not Available et est couramment utilisée en informatique pour représenter des valeurs manquantes. 
Ici, cela correspond à "aucune médaille obtenue par l’athlète").

__Note :__
Lors de la lecture du fichier, Pandas transformera ces valeurs NA, qu’il sait être des valeurs manquantes, en NaN. 
NaN signifie Not a Number, c’est la valeur qu’utilise Python pour représenter des valeurs manquantes.

Ce jeu de données va non seulement nous permettre d’illustrer l’apprentissage de l’utilisation de la librairie Pandas, 
mais nous en profiterons aussi pour l’explorer et en apprendre plus sur les Jeux olympiques.

Par exemple, les questions auxquelles nous pourrons répondre sont les suivantes :

- Quel athlète a gagné le plus de médailles d’or aux Jeux olympiques ?
- Quel pays a gagné le plus de médailles depuis le début des Jeux olympiques ?
- Quelle est l’évolution de la présence des femmes aux Jeux olympiques au fil des années ?

Tant de questions auxquelles nous pourrons répondre au cours de ce chapitre.

Ci-dessous, voici un aperçu du tableau que nous allons explorer et manipuler, afin que vous ayez visuellement en tête la structure de ce fichier. 
Nous allons le voir en détail tout au long de ce chapitre.

![image](https://github.com/user-attachments/assets/a826fe97-7d39-4c5f-8a53-95cb6b2b3862)

