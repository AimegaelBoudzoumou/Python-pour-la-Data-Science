# Les opérations mathématiques avec NumPy

## Les opérations mathématiques
Il est possible d’ajouter, de soustraire, de multiplier ou de diviser des valeurs sur un ndarray. 

Il y a des fonctions NumPy dédiées à cette tâche, ce sont les fonctions ```add()``` (ajouter), ```subtract()``` (soustraire), ```multiply()``` (multiplier) et ```divide()``` (diviser).

```python
import numpy as np
mon_tableau=np.array([[10,11,12],[13,14,15],[16,17,18]])
mon_tableau
```
```
array([[10, 11, 12],
       [13, 14, 15],
       [16, 17, 18]])
```

__add()__
```
np.add(mon_tableau,10)
```
```
array([[20, 21, 22],
       [23, 24, 25],
       [26, 27, 28]])
```

__multiply()__
Si on veut multiplier l’ensemble des valeurs par 20, on utilisera cette fois-ci la fonction multiply().
```python
np.multiply(mon_tableau,20)
```
```
array([[200, 220, 240],
       [260, 280, 300],
       [320, 340, 360]])
```

__subtract()__
```python
np.subtract(mon_tableau,4)
```
```
array([[ 6,  7,  8],
       [ 9, 10, 11],
       [12, 13, 14]])
```

__divide()__
```python
np.divide(mon_tableau,5)
```
```
array([[2. , 2.2, 2.4],
       [2.6, 2.8, 3. ],
       [3.2, 3.4, 3.6]])
```

__Calculs entre deux tableaux ndarray de taille différente__
```python
import numpy as np
mon_tableau1=np.array([[10,11,12],[13,14,15],[16,17,18]])
mon_tableau2=np.array([10,20,30])
```

```python
mon_tableau1
```

```
array([[10, 11, 12],
       [13, 14, 15],
       [16, 17, 18]])
```

```
mon_tableau2
```

```
array([10, 20, 30])
```

```python
np.subtract(mon_tableau1,mon_tableau2)
```

```
array([[  0,  -9, -18],
       [  3,  -6, -15],
       [  6,  -3, -12]])
```
Avec ce code, on enlève 10 à la première colonne du tableau mon_tableau1, on enlève 20 à la deuxième colonne de mon_tableau1 et on enlève 30 à la troisième colonne de mon_tableau1.

__Calculs entre deux tableaux ndarray de même dimensions__
```python
mon_tableau3=np.array([[1,2,3],[4,5,6],[7,8,9]])
mon_tableau3
```

```
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

```python
np.multiply(mon_tableau1,mon_tableau3)
```

```
array([[ 10,  22,  36],
       [ 52,  70,  90],
       [112, 136, 162]])
```
Ici, chaque valeur d’un tableau est multipliée par la valeur à la même position dans l’autre tableau.

## Les opérations d'agrégations
