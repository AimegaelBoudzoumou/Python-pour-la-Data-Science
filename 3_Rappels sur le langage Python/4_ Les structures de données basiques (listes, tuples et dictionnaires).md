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

```python
