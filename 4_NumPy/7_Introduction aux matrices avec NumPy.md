# Introduction aux matrices avec NumPy
Un tableau à deux dimensions peut être considéré comme une matrice. Toutefois, NumPy propose un type particulier pour bien préciser que le tableau est une matrice, il s’agit du type ```mat```.

Syntaxe pour transformer un tableau de type ```ndarray``` en matrice de type ```mat``` :

```python
import numpy as np 
ma_matrice=np.mat(mon_array)
```

La fonction ```mat()``` de NumPy permet de facilement faire cette conversion.

Il est ensuite possible de faire des opérations matricielles (multiplication par un scalaire, produit matriciel, transposition, etc.).

Voici les syntaxes des opérations matricielles élémentaires

Les matrices, tout comme les tableaux NumPy, possèdent l’attribut ```T``` pour générer la transposée de la matrice.

Mais les matrices possèdent aussi des attributs supplémentaires spécifiques, comme l’attribut ```.H``` pour générer la transposée conjuguée et l’attribut ```.I``` pour générer l’inverse de la matrice.

Syntaxe :
```python
ma_matrice.T 
ma_matrice.H 
ma_matrice.I
```

Pour obtenir le produit d’une matrice par elle-même, on utilisera la syntaxe :
```python
ma_matrice**2 
```

On obtient ainsi la matrice résultant du produit ```ma_matrice*ma_matrice```.

Note :

Si ```ma_matrice``` est de type ```ndarray``` et qu’on fait ```ma_matrice**2```, on obtient un ```ndarray``` avec tous les éléments puissance 2 : cela montre bien la nécessité de changer le type du ```ndarray``` en matrice si on souhaite effectuer des calculs matriciels !

Si on souhaite effectuer un produit matriciel sur deux ```ndarrays``` plutôt qu’une multiplication élément par élément, comme c’est le cas par défaut, il est possible d’utiliser la méthode ```dot()```. Cette méthode permet de faire le produit matriciel entre deux ```ndarrays```, sans avoir à les transformer en objet ```mat```.

```python
print("----------- array2 de base")
print(array2)

print("----------- array2 puissance 2")
# exemple de code pour obtenir un ndarray de chaque élément de array2 puissance 2 :
print(array2**2)
```
```python
----------- array2 de base
[[1. 2. 3.]
 [4. 5. 6.]
 [7. 8. 9.]]
----------- array2 puissance 2
[[ 1.  4.  9.]
 [16. 25. 36.]
 [49. 64. 81.]]
```

```python
# 3 exemples de code pour obtenir le produit matriciel d'une matrice avec elle-même 
print(np.mat(array2)**2) 
print(np.mat(array2)*np.mat(array2)) 
print(array2.dot(array2))
```

```python
# 3 exemples de code pour obtenir le produit matriciel d'une matrice avec elle-même
print("-----------")
print(np.mat(array2)**2)
print("-----------")
print(np.mat(array2)*np.mat(array2))
print("-----------")
print(array2.dot(array2))
```

```python
-----------
[[ 30.  36.  42.]
 [ 66.  81.  96.]
 [102. 126. 150.]]
-----------
[[ 30.  36.  42.]
 [ 66.  81.  96.]
 [102. 126. 150.]]
-----------
[[ 30.  36.  42.]
 [ 66.  81.  96.]
 [102. 126. 150.]]
```
