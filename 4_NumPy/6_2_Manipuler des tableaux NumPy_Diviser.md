# Manipuler des tableaux Numpy - 2/3

## 2. Diviser un tableau NumPy (split, hsplit et vsplit)
Il existe trois fonctions pour diviser un tableau avec NumPy :

- la fonction split(), utilisée pour les tableaux à une dimension,
- la fonction hsplit(), qui permet de diviser les tableaux à deux dimensions horizontalement,
- la fonction vsplit(), qui permet de diviser les tableaux à deux dimensions verticalement.

Voici la syntaxe générale de l’utilisation de ces fonctions :
```python
import numpy as np 
np.split(mon_array,index) 
np.hsplit(mon_array,index) 
np.vsplit(mon_array,index)
```

Le but ici est de "splitter", c’est-à-dire "casser/diviser" le tableau en plusieurs morceaux. 

L’index permet de dire à partir de quel index du tableau on souhaite le diviser.

### a. Sur un tableau à une dimension
Imaginons que l’on veuille couper en trois morceaux notre tableau ```notre_tableau```.

```python
import numpy as np
notre_tableau=np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20])
notre_tableau
```
```
array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
       18, 19, 20])
```

Division du tableau en trois sous-tableaux.
```python
import numpy as np

notre_tableau1, notre_tableau2, notre_tableau3 = np.split(notre_tableau, [2, 6])
```
```
print(notre_tableau1, notre_tableau2, notre_tableau3)

[1 2] [3 4 5 6] [ 7  8  9 10 11 12 13 14 15 16 17 18 19 20]
```

Ici, ```2``` et ```6``` sont les points de cassure donc on obtient trois tableaux. 

Si on avait mis un index unique et non pas une liste d’index, on aurait eu un unique point de cassure et donc deux tableaux.

### b. Sur un tableau à deux dimensions

Sur un tableau à deux dimensions, on peut diviser le tableau verticalement (```vsplit()```) ou horizontalement (```hsplit()```). 


```vsplit()``` et ```hsplit()``` ne fonctionnent que sur les tableaux à deux dimensions.

Pour l’exemple, créons un tableau à deux dimensions simple et divisons-le verticalement en deux sous-tableaux, à l’index ```2```.

```python
import numpy as np
array=np.array([[2,5,6],[9,10,11],[5,6,9]], dtype="float")
print("Avant division")
print(array)
```

```python
Avant division
[[ 2.  5.  6.]
 [ 9. 10. 11.]
 [ 5.  6.  9.]]
```

```python
array1,array2=np.vsplit(array, [2])
```

```python
print("Après division")
print(array1)
print(array2)
```

```python
Après division
[[ 2.  5.  6.]
 [ 9. 10. 11.]]
[[5. 6. 9.]]
```
Ici, on coupe verticalement en lui donnant l’index ```2```, donc on lui demande que les deux premières lignes soient mises dans un tableau et la dernière dans un autre tableau.

Enfin, visualisons ensemble une division horizontale.

```python
import numpy as np
array=np.array([[2,5,6],[9,10,11],[5,6,9]], dtype="float")
print("Avant division")
print(array)
```

```python
Avant division
[[ 2.  5.  6.]
 [ 9. 10. 11.]
 [ 5.  6.  9.]]
```

```python
array1,array2=np.hsplit(array, [2])
```

```python
print("Après division")
print(array1)
print(array2)
```

```python
Après division
[[ 2.  5.]
 [ 9. 10.]
 [ 5.  6.]]
[[ 6.]
 [11.]
 [ 9.]]
```

Là, on obtient les deux premières colonnes dans un tableau et la dernière dans un autre.
