# Exploration préliminaire d’un dataframe

a. Principaux attributs

b. Définition des termes variable, variable quantitative et variable qualitative et découverte de la méthode describe()

c. Méthodes de tri d’un dataframe

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## a. Principaux attributs

### a. 1. index

Donne la liste des index des lignes (les étiquettes des lignes) du dataframe.

Syntaxe :
```python
dataframe.index
```

### a. 2. columns

Donne la liste des noms des colonnes du dataframe.

Syntaxe :
```python
dataframe.columns
```

### a. 3. values

Génère un ndarray Numpy contenant les valeurs du dataframe.

Syntaxe :
```python
dataframe.values
```

Rappel : pour connaître le type d’un objet, il faut utiliser la fonction type().

```python
type(donnees.values) # numpy.ndarray
```

### a. 3. shape 

L’attribut shape donne des informations sur la dimension du dataframe. La sortie est un tuple contenant le nombre de lignes à gauche de la virgule et le nombre de colonnes à droite de la virgule.

__Note :__


L’ensemble des attributs et méthodes liés aux dataframes sont disponibles dans la documentation officielle : https://pandas.pydata.org/pandas-docs/version/0.21.1/generated/pandas.DataFrame.html

### a. 4. dtypes

Retourne le type des données contenues dans chaque colonne du dataframe.

__Exemple pratique__

<!-- A tester -->

```python
donnees.shape
```

```python
donnees.dtypes
```

__Note :__


Pour rappel, int64 représente des nombres entiers, float64 des nombres réels et object des chaînes de caractères (et parfois, mais pas dans notre cas, des données de types mixtes).


## b. Définition des termes variable, variable quantitative et variable qualitative et découverte de la méthode describe()

## c. Méthodes de tri d’un dataframe
