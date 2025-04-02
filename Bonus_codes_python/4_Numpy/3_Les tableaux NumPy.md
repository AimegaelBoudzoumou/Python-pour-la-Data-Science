### Ennoncé 1:
Écris une fonction en Python nommée ```creer_tableau``` qui prend en entrée une liste de listes (représentant un tableau bidimensionnel) 
et un paramètre ```dtype``` (de type chaîne) qui spécifie le type de données que le tableau doit contenir (par exemple, "int" ou "float"). 
La fonction doit créer un tableau NumPy à partir de la liste fournie en utilisant la fonction ```np.array()``` avec le type de données spécifié. 
La fonction doit retourner le tableau créé. Si le type de données fourni n'est pas "int" ou "float", la fonction doit lever une exception de type
```ValueError``` avec le message "Type de données invalide".

Par exemple, pour une entrée de ```[[1, 2, 3], [4, 5, 6]]``` et ```dtype="int"```, la fonction doit retourner un tableau d'entiers.

```python
def creer_tableau(liste_de_liste, dtype):
    """Cette fonction crée un tableau à partir d'informations qu'on lui fournit
    
    arguments : une liste de listes (représentant un tableau bidimensionnel) 
    et un paramètre dtype (de type chaîne)
    
    retourne un tableau Numpy
    """
    import numpy as np
    
    type_autorises = {"int", "float"}
    
    if dtype not in type_autorises:
        raise ValueError("Type de données invalide")
    
    return np.array(liste_de_liste, dtype = dtype)

```

### Ennoncé 2:
Écris une fonction en Python nommée ```creer_ndarray``` qui prend en entrée deux paramètres : ```dimensions``` 
(un tuple contenant le nombre de lignes et de colonnes) et ```type_array``` (une chaîne qui peut être "zeros", "ones" ou "empty"). 
La fonction doit créer un ndarray en utilisant la fonction appropriée de NumPy (np.zeros(), np.ones() ou np.empty()) selon la valeur de ```type_array```.

La fonction doit également accepter un argument optionnel ```dtype``` pour spécifier le type de données du tableau (par défaut, ce type doit être ```float```). 
Si ```type_array``` a une valeur non valide, la fonction doit lever une exception de type ```ValueError``` avec le message "Type de tableau invalide".

Par exemple, pour des entrées ```((4, 6), "zeros")```, la fonction doit retourner un tableau de zéros de type float avec 4 lignes et 6 colonnes.

```python
def creer_ndarray(dimensions, type_array, dtype=float):
    """Cette fonction crée un ndarray.
    
    arguments : dimensions (un tuple contenant le nombre de lignes et de colonnes) 
    et type_array (une chaîne qui peut être "zeros", "ones" ou "empty")
    
    retourne un ndarray
    """
    import numpy as numpy
    
    # vérfier que dimensions est bien n tuple
    
    # vérifier que les valeurs dans dimensions sont bien des nombres entiers
    
    # vérifier que type_array contient bien "zeros", "ones" ou "empty"
    
    # 
    
```

### Ennoncé 3:
Écris une fonction en Python nommée ```filtrer_tableau``` qui prend en entrée un tableau NumPy ```tableau``` et une valeur ```seuil```. 
La fonction doit retourner un nouveau tableau contenant uniquement les lignes de ```tableau``` 
pour lesquelles les valeurs de la première colonne sont supérieures au ```seuil```. La fonction doit utiliser l'indexation booléenne pour réaliser cette opération.

Par exemple, si la fonction reçoit un tableau avec les valeurs suivantes :

```
[[5.1, 3.5, 1.4, 0.2, 1.],
 [4.9, 3.0, 1.4, 0.2, 1.],
 [5.4, 3.9, 1.7, 0.4, 1.],
 [5.2, 4.0, 1.5, 0.2, 1.]]
```

et un ```seuil``` de ```5```, elle doit retourner :
```
[[5.1, 3.5, 1.4, 0.2, 1.],
 [5.4, 3.9, 1.7, 0.4, 1.],
 [5.2, 4.0, 1.5, 0.2, 1.]]
```

Assure-toi que la fonction gère correctement les cas où aucune ligne ne satisfait la condition en retournant un tableau vide.

```python
```
