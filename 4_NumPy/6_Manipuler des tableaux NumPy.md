# Manipuler des tableaux Numpy

## 1. Ajouter et supprimer des éléments dans un tableau

### a. Ajouter des éléments dans un tableau
Soit on ajoute les éléments à la fin du tableau avec la fonction ```append()``` de NumPy, 
soit on les insère à une position donnée avec la fonction ```insert()``` de NumPy.

Syntaxe :
```python
import numpy as np 
np.append(mon_array, elements_a_ajouter)
```

```python
import numpy as np

notre_tableau=np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 
       18, 19, 20])
```

```python
notre_tableau

array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
       18, 19, 20])
```

### b. Supprimer des éléments d’un tableau

## 2. Diviser un tableau NumPy (split, hsplit et vsplit)

### a. Sur un tableau à une dimension

### b. Sur un tableau à deux dimensions

## 3. Concaténer/combiner des tableaux

### a. La fonction concatenate()

### b. Les fonctions vstack() et hstack()
