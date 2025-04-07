# Manipuler des tableaux Numpy - 3/3

Trois fonctions NumPy sont disponibles pour combiner des tableaux : ```concatenate()```, ```vstack()``` et ```hstack()```.

## 3. Concaténer/combiner des tableaux
La fonction ```concatenate()``` permet de faire de la concaténation ou de la jointure de deux tableaux en NumPy.

### a. La fonction concatenate()
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
array3=np.array([[4,10,13],[7,14,15]], dtype="float")
np.concatenate([array1, array2, array3])
```

```python
array([[ 1.,  2.,  3.],
       [ 4.,  5.,  6.],
       [ 7.,  8.,  9.],
       [ 2.,  5.,  6.],
       [ 9., 10., 11.],
       [ 5.,  6.,  9.],
       [ 4., 10., 13.],
       [ 7., 14., 15.]])
```

### b. Les fonctions vstack() et hstack()
Si on souhaite combiner des tableaux de dimensions différentes, par exemple un tableau de dimension 1 avec un tableau de dimension 2, on va plutôt utiliser la fonction ```vstack()``` pour faire ce qu’on appelle un empilement vertical et la fonction ```hstack()``` pour faire un empilement horizontal.

Syntaxe:
```python
import numpy as np 
np.vstack([mon_array1,mon_array2]) 
np.hstack([mon_array1,mon_array2])
```

Pour l’exemple, on va créer un tableau de dimension 1, nommé ```array1```, et un tableau de dimension 2, nommé ```array2```, puis on va faire un empilement vertical et horizontal, pour voir ce que génèrent ces fonctions.
```python
import numpy as np
array1=np.array([15,16,47])
array2=np.array([[1,2,3],[4,5,6],[7,8,9]], dtype="float")
print(array1)
print("----------")
print(array2)
print("---------- vstack")
print(np.vstack([array1, array2]))
print("----------")
array1=np.array([[15],[16],[47]])
print("----------")
print(array1)
print("----------")
print(array2)
print("---------- hstack")
print(np.hstack([array1, array2]))
```

```python
[15 16 47]
----------
[[1. 2. 3.]
 [4. 5. 6.]
 [7. 8. 9.]]
---------- vstack
[[15. 16. 47.]
 [ 1.  2.  3.]
 [ 4.  5.  6.]
 [ 7.  8.  9.]]
----------
----------
[[15]
 [16]
 [47]]
----------
[[1. 2. 3.]
 [4. 5. 6.]
 [7. 8. 9.]]
---------- hstack
[[15.  1.  2.  3.]
 [16.  4.  5.  6.]
 [47.  7.  8.  9.]]
```

Pour l’empilement vertical, il est nécessaire que ```array1``` ait le même nombre de colonnes que ```array2```. Pour l’empilement horizontal, on redéfinit ```array1``` afin qu’il ait le même nombre de lignes que ```array2```. Pour que les empilements fonctionnent, il est en effet nécessaire de respecter les nombres de lignes pour ```hstack()``` et de colonnes pour ```vstack()```.
