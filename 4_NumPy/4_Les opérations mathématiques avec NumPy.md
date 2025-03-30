# Les opérations mathématiques avec NumPy

## Les opérations mathématiques
Il est possible d’ajouter, de soustraire, de multiplier ou de diviser des valeurs sur un ndarray. 

Il y a des fonctions NumPy dédiées à cette tâche, ce sont les fonctions ```add()``` (ajouter), ```subtract()``` (soustraire), ```multiply()``` (multiplier) et ```divide()``` (diviser).

```python
import numpy as np
mon_tableau=np.array([[10,11,12],[13,14,15],[16,17,18]])
mon_tableau
```
```python
array([[10, 11, 12],
       [13, 14, 15],
       [16, 17, 18]])
```

__add()__
```python
np.add(mon_tableau,10)
```
```python
array([[20, 21, 22],
       [23, 24, 25],
       [26, 27, 28]])
```

__multiply()__
Si on veut multiplier l’ensemble des valeurs par 20, on utilisera cette fois-ci la fonction multiply().
```python
np.multiply(mon_tableau,20)
```
```python
array([[200, 220, 240],
       [260, 280, 300],
       [320, 340, 360]])
```

__subtract()__
```python
np.subtract(mon_tableau,4)
```

```python
array([[ 6,  7,  8],
       [ 9, 10, 11],
       [12, 13, 14]])
```

__divide()__
```python
np.divide(mon_tableau,5)
```
```python
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

```python
array([[10, 11, 12],
       [13, 14, 15],
       [16, 17, 18]])
```

```python
mon_tableau2
```

```
array([10, 20, 30])
```

```python
np.subtract(mon_tableau1,mon_tableau2)
```

```python
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

```python
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

```python
np.multiply(mon_tableau1,mon_tableau3)
```

```python
array([[ 10,  22,  36],
       [ 52,  70,  90],
       [112, 136, 162]])
```
Ici, chaque valeur d’un tableau est multipliée par la valeur à la même position dans l’autre tableau.

## Les opérations d'agrégations
Lorsqu’on a un grand tableau de données, il est important de pouvoir explorer un résumé de ce tableau. La classe ```ndarray``` de NumPy possède des méthodes d’agrégation : ```sum()``` (somme), ```median()``` (médiane), ```mean()``` (moyenne), ```min()``` (minimum), ```max()``` (maximum), ```corrcoef()``` (coefficient de corrélation), ```cumsum()``` (somme cumulative) et ```std()``` (écart-type).

Ces méthodes peuvent être appliquées soit sur l’ensemble des éléments du tableau, soit par colonne ou par ligne, dans le cas de tableaux à deux dimensions. Pour cela, il suffit de préciser l’axe qu’on veut traiter avec l’option ```axis``` : ```axis = 0``` signifie qu’on veut effectuer le calcul par colonne et ```axis = 1``` signifie qu’on veut effectuer le calcul par ligne.

Syntaxe :
```python
import numpy as np 
np.sum(array) 
np.sum(array, axis=0) 
np.sum(array, axis=1) 
```

```python
import numpy as np

print("Somme de l'ensemble des éléments : ")
print(np.sum(iris))

print("Somme par colone : ")
print(np.sum(iris, axis=0))

print("Somme par ligne : ")
print(np.sum(iris, axis = 1))
```

```python
Somme de l'ensemble des éléments : 
2367.5

Somme par colone : 
[871.4 455.1 562.3 179.7 299. ]

Somme par ligne : 
[10.5 10.4 10.4 11.2 12.4 10.7 11.1  9.9 10.6 11.8 11.  10.3  9.5 12.2
 13.  12.  11.3 12.5 11.7 11.7 11.7 10.4 11.6 11.3 10.8 11.4 11.4 11.2
 10.7 10.7 11.7 11.9 12.3 10.7 10.6 11.5 11.   9.9 11.2 11.1  9.4 10.1
 11.7 12.2 10.5 11.7 10.4 11.7 10.9 18.3 17.6 18.4 15.1 17.4 16.3 17.9
 13.6 17.4 15.2 13.5 16.6 15.2 17.1 15.4 17.6 16.6 15.6 16.4 15.1 17.7
 16.2 17.2 16.8 16.9 17.4 17.8 18.4 16.9 14.8 14.8 14.6 15.6 17.4 16.4
 17.5 18.  16.3 16.  15.3 15.7 17.1 15.6 13.6 15.8 16.1 16.1 16.7 13.7
 15.9 21.1 18.5 21.1 19.6 20.5 22.3 16.6 21.3 19.8 22.4 19.8 19.3 20.4
 18.2 19.1 20.2 19.8 23.4 22.5 17.7 21.1 18.3 22.2 18.7 20.8 21.2 18.6
 18.8 19.9 20.6 21.2 23.1 20.  18.7 18.7 22.1 20.7 19.8 18.6 20.5 20.8
 20.4 18.5 21.2 21.2 20.2 18.7 19.7 20.3 18.8]
```

__Si on veut la moyenne par colonne ainsi que l’écart-type correspondant__
```python
import numpy as np
print(np.mean(iris, axis=0))
print(np.std(iris, axis=0))
```
```python
[5.84832215 3.05436242 3.7738255  1.20604027 2.00671141]
[0.82580886 0.43434487 1.75462556 0.75779867 0.81509784]
```

__Définition de l’écart-type__ : permet de mesurer la dispersion d’un ensemble de valeurs. Plus la distribution des valeurs est dispersée, plus l’écart-type sera élevé. Par rapport à la moyenne, plus l’écart-type est grand, plus les valeurs sont éloignées de la moyenne (donc moins la moyenne est représentative de ces valeurs).

__Nous allons afficher les valeurs maximales de chaque colonne du tableau iris.__
```python
import numpy as np
print(np.max(iris, axis=0))
```

```python
[7.9 4.4 6.9 2.5 3. ]
```
La longueur de sépale la plus grande est de 7.9 cm, la largeur de sépale la plus grande est de 4.4 cm, la longueur de pétale la plus grande est de 6.9 cm et la largeur de pétale la plus grande est de 2.5 cm.
