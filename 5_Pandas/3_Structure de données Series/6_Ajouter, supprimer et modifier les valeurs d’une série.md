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

## c. Modifier les valeurs d’une série

Pour modifier une valeur au sein d’une série, on pourra utiliser les indexeurs ```loc``` et ```iloc``` que nous avons vus précédemment lors de l’indexing (accès aux données). Ici, il s’agit de sélectionner la donnée qui nous intéresse via sa position ou son étiquette, puis d’y assigner une nouvelle valeur avec le symbole d’assignation ```=```.

Syntaxe :
```python
ma_serie.loc["nom_index"]=nouvelle_valeur 
```
ou
```python
ma_serie.iloc[position]=nouvelle_valeur 
```

Modifions les poids des athlètes Antti Sami Aalto et Andrzej ya dans notre série d’exemple.

```python
ma_serie_de_poids.loc[["Antti Sami Aalto"]]
ma_serie_de_poids.loc[["Antti Sami Aalto"]] = 56
ma_serie_de_poids.loc[["Antti Sami Aalto"]]
```
![image](https://github.com/user-attachments/assets/b542b314-6cc1-46dd-81e4-34a6f44a86ad)

Modification du poids de deux athlètes :
```python
ma_serie_de_poids.loc[["Antti Sami Aalto","Andrzej ya"]]=[56,70] 
ma_serie_de_poids.loc[["Antti Sami Aalto","Andrzej ya"]]
```

![image](https://github.com/user-attachments/assets/b19594c7-7020-4484-983a-c337c0cd4203)

Si un athlète est présent plusieurs fois dans une série, ce qui est le cas dans ce jeu de données puisqu’un athlète a pu participer à plusieurs JO et/ou plusieurs épreuves, son poids sera modifié à chacune de ses occurrences.

C’est le cas de l’athlète Christine Jacoba Aaftink. Regardons ses occurrences dans le jeu de données avant modification de son poids.

![image](https://github.com/user-attachments/assets/10d4016c-7533-4dfe-81c0-e45bf72c7879)

Si, pour une quelconque raison, nous voulions modifier une seule occurrence de cette athlète, alors il faudrait utiliser iloc plutôt que loc et préciser la position à laquelle modifier la valeur. En effet, une position étant unique, une seule valeur serait ainsi modifiée.
