# Introduction à NumPy

NumPy est la librairie Python dédiée au calcul scientifique fournissant des fonctions très performantes de calcul, 
mais aussi des structures de données, tout aussi performantes.

En Data Science, il est essentiel d’avoir des structures adaptées pour stocker et manipuler de grandes quantités de données. 
C’est là qu’intervient NumPy, qui intègre une nouvelle structure de données en Python, les ndarrays (tableaux à N dimensions, en français, N représentant un chiffre), 
qui sont des tableaux multidimensionnels ou matrices.

Il est important de noter que cette structure de données permet de stocker des données uniquement de même type (uniquement des nombres entiers par exemple).

Les ndarrays prennent en effet moins de place mémoire que d’autres objets Python, comme par exemple les listes.

Les ndarrays de NumPy peuvent être unidimensionnels (aussi appelés 1D array, ce qu’on peut voir comme une liste), 
bidimensionnels (2D array) donc un tableau avec des lignes et des colonnes, ou encore des tableaux à plus de deux dimensions (3D array, 4D array, 5D array...).

Pour pouvoir utiliser NumPy sous Python, il suffit de charger la librairie sous Jupyter, celle-ci étant déjà installée dans la distribution Anaconda.

```python
import numpy as np
```

Note : Il est courant d’utiliser l’alias "np" pour la librairie NumPy.
