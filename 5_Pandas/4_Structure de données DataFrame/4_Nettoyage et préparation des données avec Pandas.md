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
