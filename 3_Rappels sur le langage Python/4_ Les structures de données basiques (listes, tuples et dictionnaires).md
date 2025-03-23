# Les structures de données basiques (listes, tuples et dictionnaires)

## 1. Les listes
Une liste est un nouveau type de variable, qui permet de stocker plusieurs éléments, plusieurs valeurs, qui sont ordonnés, modifiables et peuvent être de type différent (```int```, ```float```, ```str``` ou ```bool```). 

Ainsi, on peut avoir une liste contenant uniquement des nombres entiers, uniquement des nombres réels, uniquement des chaînes de caractères, uniquement des booléens ou encore les quatre mélangés. De plus, une liste peut contenir elle-même des listes.

### a. Créer une liste

Syntaxe:
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
print(type(ma_liste)) # <class 'list'>
print(ma_liste) # [1, 2, 3, 4, 5, 6, 7, 8, 'hello', 10.5]
```

### b. Accéder aux éléments d’une liste
Pour afficher une valeur particulière d’une liste, on donnera l’index (indice) auquel se trouve la valeur qu’on souhaite afficher, c’est-à-dire la position de la valeur dans la liste.

Note : Python commence à compter à partir de 0. Donc pour afficher la première valeur de la liste, il faut donner l’index 0, pour afficher la deuxième valeur de la liste, il faut donner l’index 1, etc.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
print(ma_liste[1]) # 2
```

Plutôt que de donner un seul index, Python permet d’effectuer du slicing sur les listes, c’est-à-dire du découpage en français.

Syntaxe:
```
ma_liste[start:stop:step]
```

Ici, plutôt que d’accéder aux valeurs une par une grâce à l’indexage simple (où on ne donne qu’un index), on va donner l’index de départ, l’index de fin et le pas (par défaut le pas est de 1, si on met 2, par exemple, Python saute une valeur sur 2).

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[2:4] # [3, 4]
```

Python retourne une liste contenant les valeurs des index ```2``` et ```3```, c’est-à-dire les valeurs ```3``` et ```4``` de ```ma_liste```. Instinctivement, on pourrait penser qu’en écrivant ```2:4```, Python donnerait les valeurs aux index ```2```, ```3``` et ```4```, mais non, il donne les valeurs jusqu’à l’index ````n-1```.

Si on ne donne pas d’index au début, Python part du début de la liste.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[:4] # [1, 2, 3, 4]
```

Python affiche ````1```, ```2```, ```3``` et ```4```, les valeurs des index ```0```, ```1```, ```2```, ```3```.

Si on ne met rien comme dernier index, Python affichera la liste à partir de l’index qu’on lui donne jusqu’à la fin de la liste.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[3:] # [4, 5, 6, 7, 8, 'hello', 10.5]
```

On peut aussi donner une valeur de début, une valeur de fin et une valeur de pas. Le pas est de 1 par défaut, mais si nous le mettons à 2, Python saute une valeur sur deux.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[0:3:2] # [1, 3]
```

Voici quelques astuces de slicing supplémentaires.

Afficher les valeurs des index pairs, en partant de l’index 0 (premier index pair) jusqu’à la fin de la liste, avec un pas de 2.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[::2] # [1, 3, 5, 7, 'hello']
```

Afficher les valeurs des index impairs, en partant de l’index 1 (premier index impair) jusqu’à la fin de la liste, avec un pas de 2.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[1::2] # [2, 4, 6, 8, 10.5]
```

Si on souhaite partir de la fin de la liste, il suffit d’utiliser des nombres négatifs.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[-2] # 'hello'
```

Enfin, on peut aussi partir d’un entier positif pour arriver jusqu’à un entier négatif. 
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[1:-4] # [2, 3, 4, 5, 6]
```



### c. 
