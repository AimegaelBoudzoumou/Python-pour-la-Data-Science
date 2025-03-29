# Les tableaux NumPy

## 1. Créer un ndarray

### a. Créer un ndarray à partir de listes
On peut créer un tableau NumPy à partir d’une liste en utilisant la fonction ```array()``` afin de convertir cette liste en tableau.

```python
import numpy as np
notre_tableau=np.array([1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20])
print(notre_tableau)
type(notre_tableau)
```
```
[ 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]
numpy.ndarray
```

Pour créer un tableau __bidimensionnel__, il faut créer une __liste contenant des listes__, ce qui permet de représenter un tableau à deux entrées : les lignes et les colonnes. Pour cela, il suffit de considérer que la liste qu’on donne à la fonction array() est une liste de lignes et que les listes contenues dans cette liste représentent les colonnes. Ainsi, chaque ligne contient une liste qui correspond aux colonnes de cette ligne.

```python
import numpy as np
mon_array_bidimensionnel=np.array([[1,2,3],[4,5,6],[7,8,9]])
print(mon_array_bidimensionnel)
```

```
[[1 2 3]
 [4 5 6]
 [7 8 9]]
```
Il s’agit d’un tableau d’entiers ici, et on ne pourrait pas changer une valeur par un type caractère par exemple, cela générerait une erreur.

```python
mon_array_bidimensionnel[0,0]="texte"
```
```
ValueError: invalid literal for int() with base 10: 'texte'
```
Un ```ndarray``` ne peut contenir qu’un seul type de données. 
Pour connaître le type des données contenues dans un ```ndarray```, il suffit d’utiliser l’attribut dtype.

```python
mon_array_bidimensionnel.dtype
```
```dtype('int32')```

Il existe deux types ```int``` : ```int32``` et ```int64```. La différence entre ```int32``` et ```int64```, c’est globalement la capacité de stockage du type. ```int32``` peut stocker des nombres entiers entre -2 147 483 648 et 2 147 483 647 et ```int64``` peut stocker des nombres entiers entre -9 223 372 036 854 775 808 et +9 223 372 036 854 775 808.

### b. Créer un ndarray grâce à des fonctions NumPy


### c. Créer un ndarray à partir d’un fichier

## 2. Indexation

### a. Indexation simple

### b. Indexation booléenne

### c. Fancy indexing

## 3. Accéder aux éléments par tranche (slicing)

### a. Slicing sur un tableau NumPy à 1 dimension

### b. Slicing sur un tableau NumPy à 2 dimensions

## 4. Notion de vue et copie

