# Indexing : sélectionner des valeurs d’un dataframe

a. Indexing et slicing avec l’attribut loc

b. Indexing et slicing avec l’attribut iloc

c. Indexing avec une expression booléenne

-----------------------------------------------------------------------------------------------------------------------------------------------------------------

Pour faire de l’indexing sur les dataframes, il faut utiliser les attributs loc et iloc comme vu précédemment pour les séries.

## a. Indexing et slicing avec l’attribut loc
Pour rappel, l’attribut ```loc``` permet de sélectionner des données selon leurs étiquettes, c’est-à-dire selon les étiquettes des lignes et les noms des colonnes. La sélection se fait toujours entre crochets, mais cette fois-ci, deux ensembles de valeurs seront attendus, séparés par une virgule. Pour rappel, l’indexing permet de sélectionner une ou plusieurs valeurs, consécutives ou non.

Syntaxe pour sélectionner une valeur unique :
```python
dataframe.loc["nom_ligne","nom de colonne"] 
```

Ici, on constate qu’on accède à la valeur en donnant une étiquette d’index de ligne à gauche et un nom de colonne à droite.

Pour sélectionner plusieurs valeurs, il suffit d’utiliser des listes, avec la syntaxe suivante :
```python
dataframe.loc[["nom_de_ligne_1", "nom_de_ligne_2"], 
["nom_de_colonne", "nom_de_colonne"]]
```

Avec cette syntaxe, on sélectionnera deux valeurs, à deux lignes différentes pour une même colonne. En effet, la liste contenant les noms de colonnes, à droite de la virgule, contient deux mêmes noms de colonnes : "nom_de_colonne". Ainsi, la même colonne est sélectionnée dans cet exemple, pour deux lignes différentes.

Il est aussi possible d’utiliser le symbole ```:``` pour sélectionner une ligne spécifique et toutes les colonnes.
```python
dataframe.loc["nom_ligne",:] 
```

Pour sélectionner plusieurs lignes et toutes les colonnes, la syntaxe est la suivante :
```python
dataframe.loc[["nom_de_ligne1", "nom_de_ligne2"],:]
```

Enfin, pour sélectionner une colonne précise et toutes les lignes, la syntaxe sera la suivante :
```python
dataframe.loc[:,"nom_de_colonne"] 
```

Il est aussi possible d’utiliser la syntaxe du slicing pour récupérer des tranches de valeurs consécutives avec l’attribut ```loc```. Pour rappel, l’indexing permet de sélectionner une ou plusieurs valeurs, consécutives ou non, quand le slicing permet de sélectionner des tranches de valeurs successives.

Rappel de la syntaxe du slicing :

```python
dataframe[start:end:step] 
```

Imaginons que l’on veuille sélectionner toutes les colonnes entre deux noms de colonnes, avec un pas de 2, c’est-à-dire qu’on garde une colonne sur deux, mais qu’on veuille aussi sélectionner une tranche de lignes. La syntaxe serait la suivante :
```python
dataframe.loc['ligne1':'ligne20':1,'colonne1':'colonne10':2] 
```

Exemple pratique

Imaginons qu’on veuille regarder les informations sur le très célèbre athlète Usain Bolt. Pour cela, on peut sélectionner l’ensemble des valeurs dont l’étiquette d’index (l’étiquette de ligne) est "Usain St. Leo Bolt", de son nom complet.

```python
donnees.loc["Usain St. Leo Bolt"]
```
![image](https://github.com/user-attachments/assets/5280cc5d-1356-483c-9427-aa0247bcfae9)

Usain Bolt a participé à quatre JO, remportant huit médailles d’or sur les dix épreuves auxquelles il a participé.

Imaginons que, plutôt que de tout afficher, on souhaite simplement afficher les colonnes "Games", "Event" et "Medal" ("Jeux", "Epreuve", "Médaille").
```python
donnees.loc["Usain St. Leo Bolt",["Games", "Event", "Medal"]]
```
![image](https://github.com/user-attachments/assets/df25fe90-f11f-4907-a20c-cc7058ace08b)

Si on souhaite comparer les résultats d’Usain Bolt avec ceux de son adversaire, Justin Alexander Gatlin, il faudra utiliser le code suivant :
```python
donnees.loc[["Justin Alexander Gatlin", "Usain St. Leo Bolt"],["Games", "Event", "Medal"]]
```
![image](https://github.com/user-attachments/assets/438d1bab-b328-4894-b808-e7156d71bf59)

Justin Alexander Gatlin a, quant à lui, une médaille d’or à son actif, ainsi que deux médailles d’argent et deux médailles de bronze.

Enfin, sélectionnons des tranches de lignes et de colonnes, afin d’illustrer le slicing avec ```loc```.
```python
donnees.loc["A Dijiang":"Edgar Lindenau Aabye":1,"Age":"NOC":2]
```
Dans cet exemple, on demande de sélectionner les athlètes ```A Dijiang```, ```Edgar Lindenau Aabye``` et l’ensemble des athlètes entre ces deux-là.

Puis on demande de sélectionner les colonnes ```Age```, ```NOC``` et les colonnes entre, avec un pas de 2.
![image](https://github.com/user-attachments/assets/846e3b00-13ee-459d-a97f-5102152f09f9)

## b. Indexing et slicing avec l’attribut iloc

L’attribut iloc permet de sélectionner des valeurs selon leurs positions dans les lignes et les colonnes.

Si on souhaite sélectionner une valeur à une ligne et une colonne précise, la syntaxe est la suivante :
```python
dataframe.iloc[26,7] 
```

Pour sélectionner des valeurs à plusieurs lignes et colonnes, il faudra donner une liste de noms de lignes et une liste de noms de colonnes :
```python
dataframe.iloc[[26,65],[7,12]]
```

Pour sélectionner une ligne et toutes les colonnes, la syntaxe sera la suivante :
```python
dataframe.iloc[26,:]
```

Pour sélectionner plusieurs lignes et toutes les colonnes, il faut donner une liste de positions de ligne, comme suit :
```python
dataframe.iloc[[26,65],:] 
```

Enfin, pour sélectionner une colonne précise et toutes les lignes, la syntaxe sera la suivante :
```python
dataframe.iloc[:,7] 
```

Comme avec l’attribut loc, il est possible de faire du slicing pour sélectionner des tranches de lignes et de colonnes.

__Syntaxe:__
```python
dataframe.iloc[0:1,0:10] 
```

Ici, on sélectionne la première ligne et les dix premières colonnes du dataframe. Contrairement au slicing avec ```loc```, ici le nombre qu’on donne à l’option ```end``` n’est pas compris dans la sélection (```iloc``` s’arrête à la position 0 pour les lignes, donc sélectionne la première ligne et s’arrête à la position 9 pour les colonnes, donc sélectionne les dix premières colonnes).

## c. Indexing avec une expression booléenne

Pour faire de l’indexing avec une expression booléenne, tout comme pour les séries, il faut utiliser les opérateurs de comparaison (```>```, <, ==, !=, >=, <=) et les opérateurs bitwise&,| et ~.


