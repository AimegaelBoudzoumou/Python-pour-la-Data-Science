# Introduction

On peut décrire les dataframes comme étant des tableaux à deux dimensions, qu’on pourrait aussi comparer à une feuille Excel. Les tableaux à deux dimensions sont les structures de données les plus utilisées en analyse de données, car cela permet de représenter en ligne les individus/observations et en colonne les variables représentant ces individus/observations. Ainsi, ce qui caractérise le dataframe, ce sont son index pour les lignes et ses noms de colonnes. Son index et ses noms de colonnes permettront d’accéder aux données.

Tout comme les séries, les dataframes sont construits sur les ```ndarrays``` NumPy et possèdent donc une très bonne performance. Aussi, une colonne d’un dataframe (qui est en réalité une série) contient, dans la très grande majorité des cas, des données homogènes, de même type. En revanche, le dataframe peut contenir des données hétérogènes, puisque les colonnes sont indépendantes entre elles, chacune correspondant à une série et, en termes statistiques, à une variable. Ainsi, le dataframe peut contenir des colonnes avec des données de type ```int```, ```float```, ```bool```, etc.

Le dataframe possédant un index et des noms de colonnes, on dit aussi qu’il possède deux axes, appelés axe 0 (pour l’axe des index, ou lignes) et axe 1 (pour l’axe des colonnes). Cette notion d’axe est importante, car certaines fonctions prennent en paramètre l’axe qui est à traiter, il faut donc se rappeler que 0 signifie les lignes et 1 les colonnes. Par exemple, si on souhaite effectuer la somme de chaque colonne d’un dataframe, on utilise la fonction ```sum()``` sur l’axe ```0```. En revanche, si on souhaite avoir une somme par ligne du dataframe, on utilise la fonction ```sum()``` sur l’axe ```1```.

Voyons ensemble la structure d’un dataframe sur la figure ci-dessous :

![image](https://github.com/user-attachments/assets/84164933-5d90-44bb-a4d7-9853e4a1d305)

Pour les exemples concrets de cette section, nous allons à nouveau lire le fichier contenant les données de l’ensemble des athlètes ayant participé aux JO.

```python
import pandas as pd
donnees=pd.read_csv("120-years-of-olympic-history-athletes-and-results.csv", index_col=[1])
donnees.head()
```
![image](https://github.com/user-attachments/assets/1d57a92b-fdbb-4bba-9305-c8a851b68c96)

On vient de définir les noms d’athlètes (la colonne 1) comme étant les étiquettes d’index ; ainsi, la colonne Name devient l’index du dataframe et cet index correspond aux individus du jeu de données. 

On peut aussi voir les noms de colonnes, qui correspondent aux variables du jeu de données. Ces deux informations nous permettront de manipuler efficacement et très facilement le dataframe. 
