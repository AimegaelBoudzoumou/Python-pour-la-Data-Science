# Les tableaux NumPy

## 1. Créer un ndarray

### a. Créer un ndarray à partir de listes
On peut créer un tableau NumPy à partir d’une liste en utilisant la fonction ```array()``` afin de convertir cette liste en tableau.

```python
import numpy as np
notre_tableau=np.array([1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20])
print(notre_tableau)
type(notre_tableau)
```
```
[ 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]
numpy.ndarray
```

Pour créer un tableau __bidimensionnel__, il faut créer une __liste contenant des listes__, ce qui permet de représenter un tableau à deux entrées : les lignes et les colonnes. Pour cela, il suffit de considérer que la liste qu’on donne à la fonction array() est une liste de lignes et que les listes contenues dans cette liste représentent les colonnes. Ainsi, chaque ligne contient une liste qui correspond aux colonnes de cette ligne.

```python
import numpy as np
mon_array_bidimensionnel=np.array([[1,2,3],[4,5,6],[7,8,9]])
print(mon_array_bidimensionnel)
```

```
[[1 2 3]
 [4 5 6]
 [7 8 9]]
```
Il s’agit d’un tableau d’entiers ici, et on ne pourrait pas changer une valeur par un type caractère par exemple, cela générerait une erreur.

```python
mon_array_bidimensionnel[0,0]="texte"
```
```
ValueError: invalid literal for int() with base 10: 'texte'
```
Un ```ndarray``` ne peut contenir qu’un seul type de données. 
Pour connaître le type des données contenues dans un ```ndarray```, il suffit d’utiliser l’attribut dtype.

```python
mon_array_bidimensionnel.dtype
```
```dtype('int32')```

Note : Il existe deux types ```int``` : ```int32``` et ```int64```. La différence entre ```int32``` et ```int64```, c’est globalement la capacité de stockage du type. ```int32``` peut stocker des nombres entiers entre -2 147 483 648 et 2 147 483 647 et ```int64``` peut stocker des nombres entiers entre -9 223 372 036 854 775 808 et +9 223 372 036 854 775 808.

#### dtype
Il est possible de spécifier le type des données du tableau qu’on souhaite créer, avec l’option ```dtype``` dans la fonction ```array()``` de NumPy.

```python
import numpy as np
mon_array_bidimensionnel=np.array([[1.5,2,3], [4,5.2,6], [7,8,9.1]], dtype = float)
print(mon_array_bidimensionnel)
mon_array_bidimensionnel.dtype # dtype('float64')
```
```
[[1.5 2.  3. ]
 [4.  5.2 6. ]
 [7.  8.  9.1]]
```
```
dtype('float64')
```

### b. Créer un ndarray grâce à des fonctions NumPy
Il arrive que vous sachiez d’avance la taille de votre ndarray mais pas encore son contenu, 
car vous souhaitez remplir ce tableau au fur et à mesure de votre code. 
NumPy fournit des fonctions permettant de créer et initialiser des ndarrays de taille connue et de contenu inconnu.

#### np.zeros()
La première fonction est ```np.zeros()```. Cette fonction permet de créer un ndarray dont l’ensemble des éléments correspondent à la valeur zéro.

Syntaxe : 
```python
np.zeros((nombre de lignes, nombre de colonnes)) 
```

Il suffit de donner le nombre de lignes et de colonnes que vous souhaitez voir apparaître dans votre tableau.

```python
import numpy as np
mon_array_zeros=np.zeros((4,6))
print(mon_array_zeros)
mon_array_zeros.dtype
```
```
[[0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]
 [0. 0. 0. 0. 0. 0.]]
```
```
dtype('float64')
```

On obtient un tableau de type float, par défaut, rempli de zéros et de dimensions quatre lignes et six colonnes. Si on veut, on peut spécifier que le tableau est de type int.

```
import numpy as np
mon_array_zeros=np.zeros([4,6], dtype = int)
print(mon_array_zeros)
mon_array_zeros.dtype
```
```
[[0 0 0 0 0 0]
 [0 0 0 0 0 0]
 [0 0 0 0 0 0]
 [0 0 0 0 0 0]]
```
```
dtype('int32')
```

#### np.zeros(number)
Il est aussi possible de créer un ```ndarray``` à une dimension contenant uniquement des zéros. Pour cela, plutôt que de donner un tuple contenant le nombre de lignes et de colonnes, il suffit de donner un seul nombre à la fonction  ```np.zeros``` : ```np.zeros(5)``` créera un tableau à une dimension contenant 5 valeurs 0.

```python
import numpy as np
mon_array_zeros=np.zeros(8)
print(mon_array_zeros) # [0. 0. 0. 0. 0. 0. 0. 0.]
mon_array_zeros.dtype # dtype('float64')
```
```
import numpy as np
mon_array_zeros=np.zeros(8, dtype = int)
print(mon_array_zeros) # [0 0 0 0 0 0 0 0]
mon_array_zeros.dtype # dtype('int32')
```

#### np.ones()
Il existe ensuite la fonction ```np.ones()```. Cette fonction permet de créer un ```ndarray``` dont l’ensemble des éléments correspondent au chiffre 1.

Syntaxe :
```python
np.ones((nombre de lignes, nombre de colonnes)) 
```


```python
import numpy as np
mon_array_ones=np.ones((6,9)) # 
print(mon_array_ones)
mon_array_ones.dtype
```
```
[[1. 1. 1. 1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1. 1. 1. 1. 1.]]
```
```
dtype('float64')
```

```python
import numpy as np
mon_array_ones=np.ones((6,9), dtype = int) 
print(mon_array_ones)
mon_array_ones.dtype
```
```
[[1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1]
 [1 1 1 1 1 1 1 1 1]]
```
```
dtype('int32')
```

#### np.emptys()
Enfin, il existe la fonction ```np.emptys()```. Cette fonction permet de créer un ```ndarray``` dont les valeurs des éléments sont aléatoires.

Syntaxe :
```python
np.empty((nombre de lignes, nombre de colonnes)) 
```
```python
import numpy as np
mon_array_empty=np.empty((4,6), dtype = int)
print(mon_array_empty)
mon_array_empty.dtype
```
```
[[1405011624        692         64          0          0          0]
 [         0          0          0         57  895693618 1717645879]
 [ 962737719  925917753  828651621 1647785271  892494438  862151268]
 [ 858797669  875717475  912417893 1684104545  811872612 1700999736]]
```
```
dtype('int32')
```

### c. Créer un ndarray à partir d’un fichier
Il est aussi possible de créer un ```ndarray``` en lisant des données dans un fichier txt ou encore csv. Pour cela, nous avons besoin d’un fichier d’exemple.

Une ressource que nous utilisons est le site web : https://vincentarelbundock.github.io/Rdatasets/datasets.html qui répertorie un ensemble de jeux de données très variés, disponibles au format CSV.

Pour l’exemple, nous allons créer un tableau à partir d’un fichier de données CSV disponible via le lien suivant :
https://vincentarelbundock.github.io/Rdatasets/csv/datasets/iris.csv

Nous avons modifié ce fichier afin de pouvoir l’importer dans un ```ndarray```, qui ne doit contenir qu’un seul type de données car, à l’origine, ce fichier contient des nombres entiers et des chaînes de caractères. 
Ce fichier contient des informations sur la longueur et la largeur de pétales et de sépales de 150 iris, sous forme de nombres réels, ```float```. Les longueurs et largeurs de pétales et sépales permettent de différencier trois espèces d’Iris, représentées dans la cinquième colonne par des réels plutôt que le nom de l’espèce, étant donné que les ```ndarrays``` n’acceptent pas des types de données différents. 

L’espèce 1.0 correspond à l’espèce Setosa, l’espèce 2.0 à l’espèce Versicolor et l’espèce 3.0 correspond à l’espèce Virginica. 

Ce jeu de données est très populaire en Data Science, car il fonctionne très bien sur de nombreux modèles statistiques. Ici, nous l’utiliserons pour apprendre à créer un ```ndarray``` à partir d’un fichier, mais aussi pour apprendre à explorer et filtrer un ```ndarray``` avec NumPy.

Sur l’image ci-dessous, voici un aperçu du fichier ouvert dans Excel. Le but va être de le lire et de stocker les informations qu’il contient dans un ```ndarray```.

![iris_Capture d’écran 2025-03-29 123656](https://github.com/user-attachments/assets/0aaf6568-4bb3-4773-98a1-63be1597f5e6)


#### genfromtxt()
Pour lire un fichier, il est possible d’utiliser la fonction ```genfromtxt()``` de NumPy. Il en existe d’autres, mais celle-ci est la fonction qui possède le plus d’options, qui permettent de l’adapter à des fichiers de nombreux formats différents. 

Syntaxe:
```
mon_array=np.genfromtxt("mon_fichier.txt", delimiter=";",  
skip_header=True)
```

L’option ```delimiter``` permet de spécifier à la fonction ```genfromtxt()``` quel est le séparateur de colonne ; ici, on spécifie que les colonnes sont séparées par un point-virgule ; car il s’agit d’un fichier au format ```CSV```.

Enfin, l’option ```skip_header``` permet de spécifier à la fonction ```genfromtxt()``` que le fichier contient un en-tête et qu’on souhaite l’ignorer, en spécifiant la valeur ```True```.

```python
import numpy as np
iris=np.genfromtxt("C:/Users/chris/Documents/Travaux_personnels_2025/Python pour la Data Science/VKEIPYTDAT/EIPYTDAT/Jeux_de_donnees/iris.csv", delimiter=";", skip_header=True)
print(iris)
```
```python
[[5.1 3.5 1.4 0.2 1. ]
 [4.9 3.  1.4 0.2 1. ]
 [4.7 3.2 1.3 0.2 1. ]
 [4.6 3.1 1.5 0.2 1. ]
 [5.  3.6 1.4 0.2 1. ]
...
...
[6.7 3.  5.2 2.3 3. ]
 [6.3 2.5 5.  1.9 3. ]
 [6.5 3.  5.2 2.  3. ]
 [6.2 3.4 5.4 2.3 3. ]
 [5.9 3.  5.1 1.8 3. ]]
```

#### savetxt()
Permet d'enregistrer un fichier sur un ordinateur.

Syntaxe : 
```
np.savetxt("monarray.txt", mon_array, delimiter=";") 
```

```python
import numpy as np
np.savetxt("C:/Users/chris/Documents/Travaux_personnels_2025/Python pour la Data Science/Jeux_de_donnees/iris_2.csv", iris, delimiter=";")
```

## 2. Indexation

### a. Indexation simple

### b. Indexation booléenne

### c. Fancy indexing

## 3. Accéder aux éléments par tranche (slicing)

### a. Slicing sur un tableau NumPy à 1 dimension

### b. Slicing sur un tableau NumPy à 2 dimensions

## 4. Notion de vue et copie

