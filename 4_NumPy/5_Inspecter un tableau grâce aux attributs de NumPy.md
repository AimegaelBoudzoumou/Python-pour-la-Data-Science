# Inspecter un tableau grâce aux attributs de NumPy

Les objets de classe ```ndarray``` (les tableaux NumPy) possèdent un ensemble d’attributs qui permettent de les inspecter. La liste de ces attributs est disponible dans la documentation de NumPy, dans la partie Attributes : https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html

Voici quelques-uns attributs :
- ```dtype````: le type des éléments d’un tableau.
- ```size```: le nombre d’éléments contenus dans un tableau.
- ```T```: faire la transposée d’un tableau, c’est-à-dire de permuter les dimensions (les lignes devenant les colonnes et les colonnes les lignes)T.
- ```ndim```: connaître la dimension d’un tableau, afin de savoir s’il s’agit d’un tableau à une dimension, deux dimensions, trois dimensions, etc.
- ```shape```: connaître la taille des dimensions d’un tableau, c’est-à-dire le nombre de lignes et de colonnes.

Syntaxe d’utilisation des attributs:
```python
mon_array.attribut
```

__Note__: Pour rappel, l’attribut est une variable liée à une classe d’objets. Il permet d’accéder aux informations d’un objet de cette classe en faisant précéder l’attribut par le nom de cet objet.

```python
print("Attribut size:") 
print(iris.size)
print("Attribut shape:") 
print(iris.shape) 
print("Attribut ndim:") 
print(iris.ndim) 
print("Attribut dtype:") 
print(iris.dtype)
```

```python
Attribut size:
745
Attribut shape:
(149, 5)
Attribut ndim:
2
Attribut dtype:
float64
```

__La transposée__

```python
iris.T
```


```python
iris.T # Avec ce code, les lignes deviennent des colonnes et les colonnes des lignes
(iris.T).shape # (5, 149)
```
