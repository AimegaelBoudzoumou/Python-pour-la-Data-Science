# Manipuler des tableaux Numpy - 1/3

## 1. Ajouter et supprimer des éléments dans un tableau

### a. Ajouter des éléments dans un tableau
Soit on ajoute les éléments à la fin du tableau avec la fonction ```append()``` de NumPy, 
soit on les insère à une position donnée avec la fonction ```insert()``` de NumPy.

Syntaxe :
```python
import numpy as np 
np.append(mon_array, elements_a_ajouter)
```

__Tableaux à une dimension__

Créons l’objet notre_tableau, qui contient une suite de valeurs allant de 1 à 20 :
```python
import numpy as np

notre_tableau=np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 
       18, 19, 20])
```

Ajoutons cinq nouvelles valeurs à la suite du tableau notre_tableau :
```python
np.append(notre_tableau, [21, 22, 23, 24, 25])

array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
       18, 19, 20, 21, 22, 23, 24, 25])
```

__Tableaux à deux dimensions__

Avec un tableau à deux dimensions, on peut préciser selon quel axe on souhaite ajouter les valeurs : on peut spécifier si on souhaite ajouter une colonne, une ligne, ou encore ne rien spécifier et les éléments seront ajoutés à la suite. Attention, si on souhaite ajouter une ligne ou une colonne, il faut que ce qu’on donne comme éléments à ```append``` soit de même structure que le tableau auquel on ajoute la ligne ou la colonne.

Soit le tableau iris :
```python
import numpy as np
iris=np.genfromtxt("C:/Users/chris/Documents/Travaux_2025/Python Data Science/Jeux_de_donnees/iris.csv", delimiter=";", skip_header=True)
iris
```
```python
array([[4.9, 3. , 1.4, 0.2, 1. ],
       [4.7, 3.2, 1.3, 0.2, 1. ],
       ...
       [6.2, 3.4, 5.4, 2.3, 3. ],
       [5.9, 3. , 5.1, 1.8, 3. ]])
```

Ajouter une ligne à la fin du tableau: 
```python
np.append(iris,[[10,10,10,10,10]], axis=0)
```

```python
array([[4.9, 3. , 1.4, 0.2, 1. ],
       [4.7, 3.2, 1.3, 0.2, 1. ],
       ...
       [ 5.9,  3. ,  5.1,  1.8,  3. ],
       [10. , 10. , 10. , 10. , 10. ]])
```

Ici, les doubles crochets permettent de donner un tableau à deux dimensions en entrée à ```append()```, contenant cinq valeurs.

__Insérer une ou plusieurs valeurs à un endroit précis du tableau__

Pour insérer une ou plusieurs valeurs à un endroit précis du tableau, il faut utiliser la fonction ```insert()``` de NumPy, dont la syntaxe est la suivante :
```python
import numpy as np 
np.insert(mon_array, index, element)
```

__Tableaux à une dimension__

Exemple sur un tableau à une dimension, avec l’objet notre_tableau.
```python
import numpy as np
np.insert(notre_tableau, 1, 42)

array([ 1, 42,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
       17, 18, 19, 20])
```

On peut aussi le faire avec une liste d’éléments.
```python
import numpy as np
np.insert(notre_tableau, 1, [42,43,44,45,46])

array([ 1, 42, 43, 44, 45, 46,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12,
       13, 14, 15, 16, 17, 18, 19, 20])
```

__Tableaux à deux dimensions__
Pour utiliser cette fonction sur un tableau à deux dimensions, il faudra encore une fois respecter le bon nombre de valeurs si on précise l’axe sur lequel on souhaite insérer les nouvelles valeurs. Par exemple, si on souhaite ajouter une ligne à l’index 1 du tableau ```iris```, il faudra respecter le nombre de colonnes de ce tableau et donc donner cinq valeurs. Tout comme nous l’avons fait précédemment avec la fonction ```append()```.

iris __avant__ ```insert``` à la position 1:
```python
iris
```
```python
array([[4.9, 3. , 1.4, 0.2, 1. ],
       [4.7, 3.2, 1.3, 0.2, 1. ],
       [4.6, 3.1, 1.5, 0.2, 1. ],
       [5. , 3.6, 1.4, 0.2, 1. ],
```

```python
import numpy as np
np.insert(iris, 1, [10,10,10,10,10], axis=0)
```

iris __après__ ```insert``` à la position 1:
```python
iris
```
```python
array([[ 4.9,  3. ,  1.4,  0.2,  1. ],
       [10. , 10. , 10. , 10. , 10. ],
       [ 4.7,  3.2,  1.3,  0.2,  1. ],
       [ 4.6,  3.1,  1.5,  0.2,  1. ],
       [ 5. ,  3.6,  1.4,  0.2,  1. ],
```

Note : Pour ```append()``` comme pour ```insert()```, si on ne précise pas d’axe sur lequel ajouter les valeurs, NumPy transformera le tableau à deux dimensions en tableau à une dimension. Dans le cas de la fonction ```insert()```, NumPy ajoutera les valeurs à partir de l’index 1 de ce tableau à une dimension.

### b. Supprimer des éléments d’un tableau
Pour supprimer des éléments dans un tableau, il suffit d’utiliser la fonction ```delete()``` de NumPy.

Syntaxe :
```python
import numpy as np 
np.delete(mon_array, index, axe)
```

Si on ne précise pas l’axe, les éléments aux index donnés seront supprimés. Si on précise l’axe, par exemple ```axis=1```, ce sont les colonnes entières, aux numéros d’index spécifiés, qui sont supprimées.

iris __avant__ ```delete``` de la colonne 2 (à l’index 1):
```python
iris
```
```python
array([[4.9, 3. , 1.4, 0.2, 1. ],
       [4.7, 3.2, 1.3, 0.2, 1. ],
       [4.6, 3.1, 1.5, 0.2, 1. ],
       [5. , 3.6, 1.4, 0.2, 1. ],
       [5.4, 3.9, 1.7, 0.4, 1. ],
```

```python
import numpy as np
np.delete(iris, 1, axis = 1)
```

iris __après__ ```delete``` de la colonne 2 (à l’index 1):
```python
array([[4.9, 1.4, 0.2, 1. ],
       [4.7, 1.3, 0.2, 1. ],
       [4.6, 1.5, 0.2, 1. ],
       [5. , 1.4, 0.2, 1. ],
```

On constate que la colonne 2 (à l’index 1) a bien été supprimée.

Note : 
Il en va de même pour les lignes en spécifiant ```axis=0```. Si vous souhaitez supprimer plusieurs lignes d’un tableau, il suffit de donner une liste d’index et de spécifier ```axis=0```.

Assez logiquement, pour des tableaux à une dimension comme ```notre_tableau```, il n’y a pas besoin de spécifier l’axe. Vous pouvez supprimer une valeur à un index unique ou plusieurs valeurs en donnant une liste d’index à la fonction ```delete()```.

```python
notre_tableau

array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
       18, 19, 20])
```

```python
np.delete(notre_tableau,1)

array([ 1,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17, 18,
       19, 20])
```

La valeur ```2``` qui se trouvait à l’index ```1``` a bien été supprimée.

## 2. Diviser un tableau NumPy (split, hsplit et vsplit)

### a. Sur un tableau à une dimension

### b. Sur un tableau à deux dimensions

## 3. Concaténer/combiner des tableaux

### a. La fonction concatenate()

### b. Les fonctions vstack() et hstack()
