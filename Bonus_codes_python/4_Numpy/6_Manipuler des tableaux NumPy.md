### Ennoncé 1:

Écris une fonction en Python nommée ```ajouter_elements``` qui prend en entrée un tableau NumPy ```mon_array```, une liste ```elements_a_ajouter```, 
et un paramètre ```position``` (un entier). 

La fonction doit ajouter ```ajouter_elements``` à ```mon_array``` à la position spécifiée par ```position``` en utilisant la fonction ```np.insert()```. 
Assure-toi que si ```ajouter_elements``` est une liste de plusieurs éléments, leur longueur doit correspondre au nombre de colonnes de ```mon_array``` 
en cas d'ajout de lignes.

La fonction doit retourner le tableau modifié. Si position est en dehors des limites du tableau, la fonction doit lever une exception de type ```IndexError``` 
avec le message "Position hors limites".

Par exemple, si ```mon_array``` est un tableau à 2 dimensions avec 3 colonnes et que ```elements_a_ajouter``` est ```[10, 11, 12]``` et position est ```1```, 
la fonction doit insérer cette ligne à l'index 1.

```python
def ajouter_elements():
    """Cette fonction a pour but d'ajouter un élément à un emplacement précis d'une liste
    
    arguments : un tableau NumPy, une liste et un paramètre position (un entier).
    
    retourne le tableau modifié
    """

```

### Ennoncé 2:

Écris une fonction en Python nommée ```supprimer_elements``` qui prend en entrée un tableau NumPy ```mon_array```, une liste d'index ```indices``` à supprimer, 
et un paramètre optionnel ```axe``` (qui est 0 par défaut). La fonction doit utiliser ```np.delete()``` pour supprimer les éléments spécifiés par ```indices``` 
du tableau ```mon_array``` en fonction de l'axe spécifié.

La fonction doit retourner le tableau modifié. Si ```indices``` contient un index qui est hors limites pour ```mon_array```, 
la fonction doit lever une exception de type ```IndexError``` avec le message "Index hors limites".

Par exemple, si ```mon_array``` est un tableau à 2 dimensions et ```indices``` est ```[1, 3]```, 
la fonction doit supprimer les lignes aux index 1 et 3 si ```axe``` est 0. Si ```axe``` est 1, la fonction doit supprimer les colonnes aux index 1 et 3.

```python
```

### Ennoncé 3:

Écris une fonction en Python nommée ```combiner_tableaux``` qui prend en entrée deux tableaux NumPy, ```array1``` et ```array2```, 
et un paramètre ```mode``` qui peut être soit ```"vertical"``` soit ```"horizontal"```. 
La fonction doit utiliser ```np.vstack()``` pour combiner les tableaux si ```mode``` est ```"vertical"``` et ```np.hstack()``` si mode est ```"horizontal"```.

La fonction doit vérifier que les dimensions appropriées des tableaux sont respectées pour que la combinaison soit valide. 
Si les tableaux ne peuvent pas être combinés en fonction du mode spécifié, 
la fonction doit lever une exception de type ```ValueError``` avec le message "Dimensions incompatibles pour la combinaison".

La fonction doit retourner le tableau combiné. Par exemple, si ```array1``` est un tableau de dimension 1 avec 3 éléments et 
```array2``` est un tableau de dimension 2 avec 3 colonnes, alors l'appel de ```combiner_tableaux(array1, array2, "vertical")``` doit réussir, 
tandis que ```combiner_tableaux(array1, array2, "horizontal")``` doit lever une exception.


```python
```
