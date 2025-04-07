# Manipuler des tableaux Numpy - 3/3

Trois fonctions NumPy sont disponibles pour combiner des tableaux : ```concatenate()```, ```vstack()``` et ```hstack()```.

## 3. Concaténer/combiner des tableaux
La fonction ```concatenate()``` permet de faire de la concaténation ou de la jointure de deux tableaux en NumPy.

Syntaxe : 
```python
import numpy as np 
np.concatenate([mon_array1,mon_array2])
```
Il suffit de donner une liste de tableaux NumPy à la fonction, comme argument, pour qu’elle les concatène.

__Exemple sur des tableaux à une dimension.__

```pytho
import numpy as np
array1=np.array([1, 2, 3,4,5])
array2=np.array([6,7,8,9])
print(array1)
print(array2)
np.concatenate([array1,array2])
```
```python
[1 2 3 4 5]
[6 7 8 9]
array([1, 2, 3, 4, 5, 6, 7, 8, 9])
```
À partir de deux tableaux à une dimension, on obtient un tableau unique contenant l’ensemble des éléments des deux tableaux.

__Exemple sur des tableaux à deux dimensions.__

```python
import numpy as np
array1=np.array([[1,2,3],[4,5,6],[7,8,9]])
array2=np.array([[2,5,6],[9,10,11],[5,6,9]])
print(array1)
print(array2)
np.concatenate([array1,array2])
```
```python
[[1 2 3]
 [4 5 6]
 [7 8 9]]
[[ 2  5  6]
 [ 9 10 11]
 [ 5  6  9]]
array([[ 1,  2,  3],
       [ 4,  5,  6],
       [ 7,  8,  9],
       [ 2,  5,  6],
       [ 9, 10, 11],
       [ 5,  6,  9]])
```

Les deux tableaux sont bien concaténés, l’un en dessous de l’autre. Bien sûr, pour pouvoir faire ça il faut, en toute logique, respecter les dimensions. Par exemple ici, les deux tableaux ont le même nombre de colonnes, donc ça marche bien.

On peut aussi concaténer plus de deux tableaux à la fois.

```python
```

### a. La fonction concatenate()

### b. Les fonctions vstack() et hstack()
