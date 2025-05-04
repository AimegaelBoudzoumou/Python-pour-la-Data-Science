# Les attributs et les méthodes des objets de classe Series

Les objets de classes Series possèdent des attributs et des méthodes qui sont très utiles lorsqu’on souhaite les analyser. L’ensemble des méthodes et des attributs existants n’est pas couvert, mais vous pouvez tous les retrouver dans la documentation Python sur les objets de classe Series : https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html

## a. Les attributs des objets de classe Series
Pour rappel, en Python, chaque classe a ses propres attributs, qui sont des variables appartenant à cette classe et permettant d’obtenir rapidement des informations au sujet d’un objet de cette classe. Il existe donc un ensemble d’attributs pour les objets de classe ```Series```, dont voici quelques exemples :

- ```dtype``` : retourne le dtype, c’est-à-dire le type des données contenues dans la série.

- ```iloc``` et ```loc``` : permettent d’accéder aux valeurs de la série, par position ou par étiquette.

- ```index``` : retourne les index de la série.

- ```values``` : retourne les valeurs de la série.

- ```name``` : retourne le nom de la série.

- ```size``` : retourne le nombre de valeurs contenues dans la série, c’est-à-dire sa taille.

__Pratiquons__

Déterminons la taille de notre série contenant le poids des athlètes.

```python
import pandas as pd
ma_serie_de_poids=pd.read_csv(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\JO_Dataset\athlete_events.csv", usecols=["Weight"])
ma_serie_de_poids = ma_serie_de_poids.squeeze()
ma_serie_de_poids.size
```
![image](https://github.com/user-attachments/assets/b570a875-4285-4670-9a7e-a651bcd42cac)

![image](https://github.com/user-attachments/assets/96975d7c-5483-46db-8097-90349ab23d5e)

Pour rappel, les attributs sont des variables et s’appellent donc sans parenthèses, contrairement aux méthodes.

## b. Les méthodes des objets de classe Series

Pour rappel, en Python, chaque classe a ses propres méthodes, qui peuvent être comparées à des fonctions capables de manipuler cette classe d’objets précisément. La différence entre les méthodes, spécifiques à une classe, et les fonctions, applicables à plusieurs classes, est la manière de les appeler. Une méthode s’appellera de la manière suivante.

```python
ma_serie.methode()
```
alors que la fonction s’appellera de la manière suivante :
```python
fonction(ma_serie)
```

Il existe énormément de méthodes pour les séries ; toutes sont accessibles dans la documentation liée aux séries : https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html

Il existe donc un ensemble de méthodes pour les objets de classe ```Series```, dont voici quelques exemples :

- ```describe()``` : permet d’afficher un résumé statistique sur les valeurs de la série.

- ```value_counts()``` : permet de visualiser les valeurs uniques ainsi que leur nombre au sein de la série.

- ```replace()``` : permet de remplacer une ou plusieurs valeurs par une autre au sein d’une série.

- ```set_index()``` : permet de redéfinir les index de la série.

__Pratiquons__

Imaginons que l’on veuille un résumé statistique de tous les poids de notre série, il faudra utiliser la méthode ```describe()```.

__Note__

La méthode ```describe()``` est très utilisée pour avoir un premier aperçu de vos données en générant des statistiques descriptives.

```python
import pandas as pd
ma_serie_de_poids=pd.read_csv(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\JO_Dataset\athlete_events.csv", usecols=["Weight"])
ma_serie_de_poids = ma_serie_de_poids.squeeze()
ma_serie_de_poids.describe()
```
![image](https://github.com/user-attachments/assets/fcc62b38-4a9c-4c1c-9d83-f519d90e2d69)

Cette méthode fournit différentes statistiques. La première, ```count```, donne le nombre de valeurs dans la série, sans compter les valeurs manquantes. Nous savons que la taille de notre série est de ```271  116``` valeurs, et maintenant nous savons que ```208  241``` valeurs ne sont pas des valeurs manquantes. Ensuite, ```70.70``` correspond à la valeur moyenne (```mean```) des poids dans notre série, avec une déviation standard (`````std```) de ```14``` (moyenne de 70 kg +/- 14 kg). Le poids minimal dans ce jeu de données est de 25 kg (```min```) et le poids maximal (```max```) de 214 kg. Enfin, nous avons les quartiles, qui permettent de diviser les données en quatre parts égales. L’interprétation est la suivante : 25 % des athlètes font moins de 60 kg, 50 % des athlètes font moins de 70 kg et 75 % des athlètes font moins de 79 kg.
