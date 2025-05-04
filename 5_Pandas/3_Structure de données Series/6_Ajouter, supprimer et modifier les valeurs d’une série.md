# Ajouter, supprimer et modifier les valeurs d’une série

## a. Ajouter des valeurs à une série

Pour ajouter une ou des valeurs à une série, on utilise généralement la méthode ```append()```. Cette méthode permet en réalité de concaténer deux ou plusieurs séries ; nous allons voir comment l’utiliser pour ajouter des valeurs à une série, à la volée.

__Note__ 

La méthode ```append()``` est dépréciée par Python.

Le code suivant :
```python
ma_serie_de_poids=ma_serie_de_poids.append(pd.Series([90,120],  
index=["Claire Muller", "Julien Villeroy"])) 
ma_serie_de_poids.loc[["Claire Muller","Julien Villeroy"]]
```
provoque cette erreur :

```
AttributeError: 'Series' object has no attribute 'append'
```

A la place, utilisons ```loc```:

```python
ma_serie_de_poids.loc["Claire Muller"] = 90.0
ma_serie_de_poids.loc["Julien Villeroy"] = 120.0
```

```python
ma_serie_de_poids
```

![image](https://github.com/user-attachments/assets/7220a498-c238-43fa-9faf-f88614f7ef81)


## b. Supprimer une valeur d’une série

Pour supprimer une valeur d’une série, on utilisera la méthode ```drop()``` qui permet de supprimer les valeurs aux étiquettes d’index spécifiées en option.

Syntaxe :
```python
ma_serie.drop(labels=["index1", "index2"], inplace=False) 
```

L’option ```labels``` attend une liste de noms d’index à supprimer.

L’option ```inplace``` est intéressante : par défaut, elle est à ```False```. Si cette option est à ```False```, la méthode ```drop()``` retourne une copie de ma_serie, avec la modification effectuée. Si on met l’option à ```True```, la méthode ```drop()``` effectue la modification directement sur l’objet ```ma_serie``` et ne retourne donc pas de copie.

```python
ma_serie_de_poids.drop(labels=["Claire Muller","Julien Villeroy"], inplace=True)
```

```python
ma_serie_de_poids
```

![image](https://github.com/user-attachments/assets/aecf1b28-ad8f-49cf-8a74-5c86bdf4557d)

```python
ma_serie_de_poids.loc[["Claire Muller","Julien Villeroy"]]
```
```
KeyError: "None of [Index(['Claire Muller', 'Julien Villeroy'], dtype='object', name='Name')] are in the [index]"
```

L'erreur ci-dessus est normal, car les labels "```Claire Muller```" et "```Julien Villeroy```" ont été supprimés de la série.

