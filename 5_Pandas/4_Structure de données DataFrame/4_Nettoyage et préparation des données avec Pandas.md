# Nettoyage et préparation des données avec Pandas

a. Gestion des données manquantes

b. Gestion des données dupliquées

------------------------------------------------------------------------------------------------------------------------------------------------------------------

Avant de pouvoir explorer les données contenues dans un tableau, il faut le nettoyer, le préparer. Il y a deux étapes importantes, avant toute chose : prendre en compte les valeurs manquantes, et les traiter au besoin, mais aussi les valeurs dupliquées, et les supprimer si besoin.

## a. Gestion des données manquantes
Lorsqu’une donnée ne peut pas être répertoriée, lorsque la valeur dans le dataframe est vide, sa valeur devient ```NaN```. Il est important de prendre connaissance de la proportion des valeurs manquantes, voire de les traiter, ce que nous allons voir dans cette section.

### isna()

La syntaxe générale pour compter le nombre de valeurs manquantes dans un dataframe est la suivante :
```python
mon_dataframe.isna().sum() 
```

__Pratiquons__
```python
donnees.isna().sum()
```

![image](https://github.com/user-attachments/assets/9e94706a-9f39-4c0f-accd-dc6376c02cc4)

Remarque : pour 3.5 % du jeu de données, l’âge n’est pas renseigné.

3.5 = 9474 * 100 / 271166

### dropna() : Suppression des valeurs manquantes

Il peut arriver que la suppression des lignes contenant des NaN soit utile, si on veut uniquement considérer les données pour lesquelles les valeurs sont présentes.

__Note :__

Dans les chapitres sur la visualisation de données avec les librairies Matplotlib et Seaborn, nous verrons ensemble dans quel cas il est intéressant de supprimer les valeurs manquantes et dans quel cas il faut impérativement les garder, sous peine de perdre de l’information.

Pour supprimer les lignes contenant un NaN dans au moins une colonne ou toutes les colonnes, il existe la méthode dropna().

Syntaxe : 
```python
dataframe.dropna(how="any") 
```

L’option ```how="any"``` permet de spécifier à la méthode ```dropna()``` que si une seule valeur de la ligne est égale à ```NaN```, alors il faut supprimer cette ligne.

Il est aussi possible de supprimer les lignes si l’ensemble des valeurs sont à ```NaN```, c’est-à-dire si la valeur ```NaN``` est présente dans l’ensemble des colonnes, grâce à l’option ```how="all```".

Syntaxe :
```python
dataframe.dropna(how="all")
```

### notna()
Pour supprimer les lignes avec une valeur manquante dans une colonne spécifique, il faudra utiliser la méthode ```notna()``` plutôt que la méthode ```dropna()```.

Syntaxe
```python
dataframe[dataframe['ma_colonne'].notna()] 
```

__Exemple pratique__

Dans le cas où on veut étudier uniquement la taille des athlètes ayant participé aux JO, il serait plutôt utile de supprimer les athlètes dont la taille n’est pas répertoriée dans le jeu de données. Ainsi, nous allons supprimer les lignes avec une valeur manquante dans la colonne ```Height```.
```python
# Nous allons supprimer les lignes avec une valeur manquante dans la colonne ```Height```.

donnees[donnees['Height'].notna()]
```

![image](https://github.com/user-attachments/assets/460c52be-db47-4796-86f5-588c646b33b5)

### fillna() : Remplacement des valeurs manquantes

Il peut arriver que nous n’ayons pas envie de supprimer les lignes contenant des valeurs manquantes, sous peine de perdre de l’information, mais qu’on souhaite toutefois ne plus avoir de valeurs manquantes dans le tableau. Il est alors possible d’utiliser une méthode appelée ```fillna()```, qui va remplacer les valeurs ```NaN``` par ce qu’on lui demande.

Par exemple, si on souhaite remplacer l’ensemble des ```NaN``` par 0, la syntaxe est la suivante :
```python
dataframe.fillna(value=0, inplace=True) 
```

On peut aussi remplacer les valeurs ```NaN``` par la moyenne de la colonne dans laquelle la valeur se trouve, avec la syntaxe suivante :
```python
dataframe[['colonne1', 'colonne4']] =  
dataframe[['colonne1','colonne4']].fillna(dataframe[['colonne1', 
'colonne4']].mean())
```

__Pratiquons__
Remplaçons les valeurs manquantes des colonnes Age, Height et Weight par la valeur moyenne de chaque colonne, respectivement.

```python
donnees_modif = donnees.copy()

# Remplaçons les valeurs manquantes des colonnes Age, Height et Weight par la valeur moyenne de chaque colonne, respectivement.

donnees_modif[["Age", "Height", "Weight"]] = donnees_modif[["Age", "Height", "Weight"]].fillna(donnees_modif[["Age", "Height", "Weight"]].mean())

donnees_modif
```

__Note :__
```python
donnees[['Age','Height','Weight']].mean()
```
![image](https://github.com/user-attachments/assets/15f3a444-c83e-4038-8cd9-051c98495a85)

Il s’agit d’une série contenant pour chaque variable la moyenne des valeurs de cette variable.

## b. Gestion des données dupliquées

Lorsqu’on commence à travailler avec un tableau contenant beaucoup de données, il ne faut pas seulement prendre en compte la gestion des valeurs manquantes, mais aussi celle des informations dupliquées. En effet, cela peut fausser les conclusions que l’on fait sur un jeu de données si certaines informations sont dupliquées de nombreuses fois.

Des informations dupliquées peuvent être des lignes entières dupliquées, c’est-à-dire que, pour une raison inconnue, une ligne a été entrée dans le tableau deux fois, voire plus. C’est ce genre d’erreur qui peut poser problème, il faut donc faire attention et les traiter.

### b.1. Détection/récupération des lignes dupliquées

La syntaxe générale pour détecter les lignes entièrement dupliquées dans un tableau est la suivante :
```python
dataframe[dataframe.duplicated()] 
```

Ici, on utilise la méthode ```duplicated()``` qui retournera une série contenant des booléens permettant de dire si la ligne est dupliquée (```True```) ou non (```False```). Ainsi, la syntaxe présentée retournera l’ensemble des lignes dupliquées, sauf la première occurrence. En effet, la méthode ```duplicated()``` possède deux options intéressantes, dont voici la syntaxe :
```python
dataframe[dataframe.duplicated(subset=["ma_colonne1",ma_colonne2"], 
keep='first')]
```

### b.2. Détecter la duplication sur un sous-ensemble de colonnes
Par défaut, la méthode ```duplicated()```, traite les lignes entières, c’est-à-dire l’ensemble des colonnes. Si on souhaite uniquement détecter la duplication sur un sous-ensemble de colonnes, il est possible de donner les noms de colonnes à l’option ```subset```.

De même, par défaut, la méthode ```duplicated()``` garde la première occurrence de lignes dupliquées et supprime les autres, grâce à l’option ```keep=’first’```. Ainsi, quand on utilise la syntaxe présentée ci-dessus, celle-ci retourne un dataframe contenant l’ensemble des lignes dupliquées (dont la valeur est ```True``` après ```duplicated()```), sauf la première occurrence, que ```duplicated()``` laisse à ```False``` pour ne pas perdre l’information.

En effet, la suppression de données dupliquées nécessite tout de même de garder une occurrence des données dupliquées. Il est aussi possible de garder uniquement la dernière occurrence des lignes dupliquées avec l’option ```keep=’last’```. Dans ce cas, c’est la dernière occurrence que la méthode ```duplicated()``` laisserait à ```False``` et les autres à ```True```.

__Exemple pratique__

Récupérons les lignes dupliquées dans le tableau donnees.
```python
donnees[donnees.duplicated()]
```
![image](https://github.com/user-attachments/assets/4679d022-a8e2-4ae9-bce3-1b4da8f5b829)

Ici, l’ensemble des lignes dupliquées avec toutes leurs occurrences, sauf la première, sont retournées. Avec ce résultat, on peut conclure que la ligne avec l’ID ```704``` est présente deux fois dans le tableau, puisque la méthode ```duplicated()``` l’affiche une fois, sans la première occurrence. La ligne avec l’ID ```2449``` est présente trois fois dans le tableau, avec exactement les mêmes valeurs dans l’ensemble des colonnes. La présence de ces lignes dupliquées fausse clairement les résultats, car si on s’intéresse par exemple à la discipline "Art Competitions" et que l’on compte le nombre d’athlètes dans cette discipline, le résultat sera supérieur à la réalité puisqu’il y a des lignes dupliquées. C’est pour cela qu’il est important de nettoyer son jeu de données avant de commencer à l’analyser, pour ne pas faire de fausses conclusions.

### Attention
Ici ce sont vraiment des lignes dupliquées entièrement, donc de l’information dupliquée. Dans ce tableau, on sait que les athlètes peuvent être présents plusieurs fois, car ils ont pu participer à plusieurs JO et/ou plusieurs épreuves, mais pour ces cas précis, l’ensemble de la ligne n’est pas dupliqué, les variables ```Year``` ou ```Event```, au minimum, changent. Donc on ne les récupère pas ici. Le but est réellement de détecter les lignes apportant exactement la même information plusieurs fois.

### b. 4. Compter le nombre de lignes dupliquées dans le tableau
Pour compter le nombre de lignes dupliquées dans le tableau, il suffit d’utiliser l’attribut ```shape``` sur notre code précédent. L’attribut ```shape``` est une variable retournant un tuple contenant la dimension d’un dataframe : (```nombre de lignes```, ```nombre de colonnes```).
```python
donnees[donnees.duplicated()].shape
```
![image](https://github.com/user-attachments/assets/3818a5ca-88d7-4e8c-a1c7-ffb3d4f1dd31)

Il y a en tout 1 385 lignes dupliquées dans le tableau, sans compter leur première occurrence, et qu’il faudrait supprimer.

### b. 5. Suppression des lignes dupliquées
Pour nettoyer le dataframe, on va vouloir supprimer l’ensemble des lignes dupliquées, en gardant toujours une occurrence de celles-ci.

La syntaxe générale pour faire cette étape de nettoyage est la suivante :
```python
dataframe.drop_duplicates(inplace=True) 
```

La méthode ```drop_duplicates()``` va supprimer les lignes dupliquées en prenant en compte l’ensemble des colonnes et en gardant la première occurrence de chaque ligne dupliquée dans le dataframe qu’elle retourne.

Cette méthode possède les deux mêmes options que la méthode ```duplicated() : keep``` pour garder la première ou la dernière occurrence et ```subset``` pour préciser quelles colonnes prendre en compte pour déterminer les lignes dupliquées, la méthode prenant par défaut l’ensemble des colonnes.

En ne précisant pas l’option ```inplace```, la méthode ```drop_duplicates()``` retourne une copie du dataframe d’origine, sans lignes dupliquées. En précisant l’option ```inplace=True```, la méthode ```drop_duplicates()``` supprime les lignes dupliquées directement sur le dataframe d’origine.

__Exemple pratique__

Supprimons les lignes dupliquées du jeu de données des JO.

![image](https://github.com/user-attachments/assets/1f7f5e87-5136-4426-b03e-ad64a7bb80fa)

