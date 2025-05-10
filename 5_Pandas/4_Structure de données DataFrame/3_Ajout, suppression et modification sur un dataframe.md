# Ajout, suppression et modification sur un dataframe

a. Ajouter une ou plusieurs colonnes à un dataframe

b. Ajouter une ligne à un dataframe

c. Supprimer des lignes ou colonnes d’un dataframe

d. Modifier des valeurs dans un dataframe

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## a. Ajouter une ou plusieurs colonnes à un dataframe

### Méthode 1 :
La première, qui est la plus simple au niveau syntaxique, permet d’ajouter une colonne à partir d’une liste ou d’une série, cette colonne s’ajoutant à la fin du dataframe.

__Syntaxe__
```python
dataframe['nouvelle colonne'] = [ma_valeur1, ma_valeur_2, ...] 
dataframe['nouvelle colonne'] = ma_serie
```

Attention, il faut que le nombre de valeurs dans votre liste ou dans votre série soit de même taille que le nombre de lignes dans votre dataframe.

Si vous souhaitez ajouter une colonne contenant la même valeur à chaque ligne, pour, par exemple, modifier ces valeurs plus tard dans votre code, il est alors possible de donner une liste contenant une valeur unique et cette valeur sera alors la même dans toute la colonne.

__Syntaxe__
```python
dataframe['nouvelle colonne']=[0] 
```

### Méthode 2 :
La deuxième méthode d’ajout de colonne consiste à utiliser la méthode insert() de Pandas. L’avantage de cette méthode est qu’on peut choisir la position à laquelle insérer la nouvelle colonne, plutôt que de l’ajouter à la fin du dataframe.

__Syntaxe__
```python
dataframe.insert(0, 'Nom_de_colonne', [1, 2, 3]) 
dataframe.insert(0, 'Nom_de_colonne', ma_serie)
```

__Exemple pratique__
Créons une copie de notre objet ```donnees``` appelée ```donnees_test```, auquel nous ajouterons une colonne nommée ```Test``` contenant la valeur ```0```, dans le dataframe des Jeux olympiques, à la fin du tableau :

```pyton
donnees_test = donnees.copy()
donnees_test["Test"] = 0
donnees_test
```
![image](https://github.com/user-attachments/assets/2bc4fbf5-7b49-44cf-aede-87fc188d1e47)

Utilisons la méthode ```insert()``` pour ajouter notre série contenant le poids des athlètes, ```ma_serie_de_poids```, comme colonne nommée ```Poids_athlètes```, en troisième position du dataframe ```donnees_test```.

Récupérons d'abord les poids :
```python
import pandas as pd
ma_serie_de_poids = pd.read_csv("athlete_events.csv", usecols=[5])
ma_serie_de_poids = ma_serie_de_poids.squeeze()

ma_serie_de_poids
```

![image](https://github.com/user-attachments/assets/336b036d-6bae-419b-8851-6b664e8ba90a)

Ensuite :
```python
donnees_test.insert(2, "Poids_athlètes", ma_serie_de_poids.values)

donnees_test
```

![image](https://github.com/user-attachments/assets/dcb09e88-5743-45bd-9c9d-eb53161e6a68)

## b. Ajouter une ligne à un dataframe


## c. Supprimer des lignes ou colonnes d’un dataframe

## d. Modifier des valeurs dans un dataframe
