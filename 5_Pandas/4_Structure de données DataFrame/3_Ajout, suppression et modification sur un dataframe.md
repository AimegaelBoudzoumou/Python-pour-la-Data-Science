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

__Note importante__
Le livre présente l'utilisation de ```append```. 

L'utilisation de ```append``` provoque cette erreur :
```python
AttributeError: 'DataFrame' object has no attribute 'append'
```

Je recommande d'utiliser ```loc```.

```python
import pandas as pd

donnees.loc["Claire Muller"] = pd.Series(['135572', 'F', 29, 
175, 58, 'China', 'CHN', '2012 Summer', 2012, 'Summer', 'London', 
'Judo', "Judo Women's Extra-Lightweight",'NaN' ], index=donnees.columns)

donnees.tail()
```
![image](https://github.com/user-attachments/assets/882a89bf-fb24-4a6d-a626-2faff5ecfb1d)

<!--
Pour ajouter une ou plusieurs lignes, on utilise la méthode append() que nous avons déjà rencontrée sur les objets de classe Series.

__Syntaxe d’ajout d’une ligne__
```python
import pandas as pd 
dataframe_nouveau=dataframe.append(pd.Series([valeur1, valeur2, ...], 
index=dataframe.columns),ignore_index=True)
```

__Note__
Si les index de votre dataframe correspondent à des nombres incrémentés et que vous souhaitez rester là-dessus, définissez une série sans nom au sein de la méthode ```append()``` et utilisez l’option ```ignore_index=True```. En revanche, si vous donnez un nom à la série créée dans ```append()```, grâce à l’option ```Name``` que nous avons vue ensemble dans la section sur les séries, et que vous souhaitez que ce nom précisément apparaisse comme étiquette de la nouvelle ligne ajoutée, alors laissez l’option ```ignore_index=False```.

Pour ajouter plusieurs lignes, il suffit de donner une liste de séries à la méthode ```append()```.

Syntaxe :

```python
dataframe_nouveau=dataframe.append([pd.Series([valeur1, valeur2, ...], 
index=dataframe.columns), pd.Series([valeur1_2, valeur2_2, ...], 
index=index_colonnes), pd.Series([valeur1_3, valeur2_3, ...],  
index=index_colonnes) ], ignore_index=True)
```

Il est possible de donner un nom aux séries, à utiliser comme index des nouvelles lignes.

Syntaxe
```python
dataframe_nouveau=dataframe.append([pd.Series([valeur1, valeur2, ...], 
index=dataframe.columns, name="index_de_ligne_1"),  
pd.Series([valeur1_2, valeur2_2, ...], index=index_colonnes,  
name="index_de_ligne_2"), pd.Series([valeur1_3, valeur2_3, ...],  
index=index_colonnes, name="index_de_ligne_3") ])
```

__Note__

Comme expliqué lors de la première utilisation de la méthode append(), celle-ci n’effectue pas la modification directement sur le dataframe mais crée une copie de ce dataframe, pour ne pas toucher à l’intégrité des données du dataframe original. Ainsi, il faut ranger le nouveau dataframe que retourne la méthode append() dans une nouvelle variable.

__Exemple pratique 1__
Code pour ajouter une ligne, avec l’option ignore_index=True

__Exemple pratique 2__
Code pour ajouter une ligne, avec l’option ignore_index=True
-->

## c. Supprimer des lignes ou colonnes d’un dataframe

Pour la suppression d’éléments dans un dataframe, que ce soit des lignes ou des colonnes, il faut utiliser la méthode ```drop()```. Pour les colonnes, il faut utiliser le ou les noms de colonnes à supprimer en spécifier l’axe d’intérêt, ici l’axe des colonnes, donc 1.

Syntaxe de suppression de colonnes avec la méthode drop()
```python
dataframe_nouveau=dataframe.drop(["ma_colonne_1","ma_colonne_2", 
"ma_colonne_3"], axis=1)
```

Pour supprimer des lignes, on utilisera soit leur position, soit leur étiquette d’index.

__soit leur étiquette d’index__
Pour supprimer des lignes via leur étiquette, on donnera ces étiquettes sous forme de liste en spécifiant l’axe des lignes, ici 0.

__Syntaxe__
```python
dataframe_nouveau=dataframe.drop(["ma_ligne_1","ma_ligne_2", 
"ma_ligne_3"], axis=0) 
```

__soit leur position__
Pour supprimer des lignes via leurs positions, on utilisera la méthode ```index()``` au sein de la méthode ```drop()```, avec la syntaxe suivante :
```python
dataframe_nouveau=dataframe.drop(dataframe.index[[2,3]], axis=0) 
```

La méthode ```index()``` permet de récupérer les étiquettes des index en donnant leur position. Ainsi, dans cet exemple, on récupère les étiquettes des lignes aux positions 2 et 3, qu’on donne ensuite à la méthode ```drop()``` pour qu’elle puisse les supprimer.

__inplace dans drop()__
La méthode drop() retourne une copie du dataframe avec les éléments supprimés, afin de ne pas modifier le dataframe original. Toutefois, il est possible d’utiliser l’option inplace=True pour effectuer la suppression directement sur le dataframe original.

Syntaxe :
```python
dataframe.drop(["ma_colonne_1","ma_colonne_2","ma_colonne_3"],  
axis=1, inplace=True) 
```

__Exemple pratique 1__
Supprimons les colonnes nommées ```Test``` et ```Poids_athlètes``` précédemment ajoutées sur le dataframe nommé ```donnees_test```.

```python
donnees_test.drop(["Test", "Poids_athlètes"], axis=1, inplace=True)

donnees_test.head()
```

![image](https://github.com/user-attachments/assets/40ce7b73-219e-4f49-9ceb-4d6a71da0583)

__Exemple pratique 2__
Comme deuxième exemple, supprimons la dernière ligne ajoutée à notre jeu de données sur les JO, dont le dataframe ```donnees```. L’étiquette de cette ligne est "Claire Muller" et on peut l’utiliser pour supprimer la ligne.
__Avant suppression :__
```python
donnees.tail()
```
![image](https://github.com/user-attachments/assets/b4b00f7f-af5e-4be5-a7e4-5ecccc8585fa)

__Suppression "Claire Muller"__
```python
donnees.drop(["Claire Muller"], axis=0, inplace=True)
```

__Après suppression :__
```python
donnees.tail()
```
![image](https://github.com/user-attachments/assets/7d11bb1e-6d43-40b8-84cc-5309db36566b)


## d. Modifier des valeurs dans un dataframe
