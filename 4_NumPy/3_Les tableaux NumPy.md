# Les tableaux NumPy

Contenu :

Créer un ndarray : à partir d'une liste, grâce à des fonctions Numpy, à partir d'un fichier

Indexation : indexation simple, indexation booléenne, Fancy indexing

Accéder aux éléments par tranche

Notion de vue et de copie

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
L’indexation simple permet d’accéder à un élément unique d’un tableau. Un peu comme pour les liste en Python, on utilise les crochets ```[]```.

Syntaxe pour un __ndarray à une dimension__
```python
mon_array[2] # permet d’accéder à la troisième valeur du tableau mon_array; car on commence à compter à partir de 0 en Python
```

Syntaxe pour un __ndarray à deux dimension__
```python
mon_array[2,1] # permet d’accéder à la valeur située à la troisième ligne, deuxième colonne du tableau mon_array.
```

Pour __modifier__ une valeur d’un ndarray
```python
mon_array[2,1]=10
```

```python
import numpy as np
iris=np.genfromtxt("C:/Users/chris/Documents/Travaux_personnels_2025/Python pour la Data Science/Jeux_de_donnees/iris.csv", delimiter=";", skip_header=True)
#print(iris)
iris[2,1] # 3.1
```

Modification de valeur : 
```python
iris[2,1]=4
iris[2,1] # 4.0
```

### b. Indexation booléenne
Contrairement à l’indexation simple, où on va utiliser les positions des valeurs pour les récupérer, 
ici, nous allons utiliser des masques booléens (masks, en anglais) pour sélectionner une portion du tableau. 

Comme nous l’avons vu dans les rappels sur Python, 
les opérateurs relationnels vont pouvoir être utilisés ici pour faire ce qu’on appelle une indexation booléenne.

Imaginons que l’on souhaite garder uniquement les valeurs d’un tableau qui sont supérieures à la valeur 10, la syntaxe serait la suivante :
```python
mon_array[mon_array > 10] 
```

La condition ```mon_array > 10``` va générer un ```ndarray```, de même dimension que le tableau qu’on cherche à indexer, contenant des valeurs booléennes. Ce tableau de valeurs booléennes permettra à Python de savoir quelles valeurs de ```mon_array``` garder : celles aux positions où la valeur est à ```True``` dans le ```ndarray``` généré par ```mon_array > 10```.

Affichons ce que génère le masque booléen iris >2:
```python
iris > 2
```

```python
array([[ True,  True, False, False, False],
       [ True,  True, False, False, False],
       ...
       ...
       [ True,  True,  True,  True,  True],
       [ True,  True,  True, False,  True]])
```

Cette expression booléenne ```mon_array > 10``` génère un nouveau tableau, de même dimension que le tableau ```iris```, mais qui contient uniquement des booléens, ```True``` ou ```False```. Python sait qu’il doit garder uniquement les valeurs du tableau ```iris``` aux index pour lesquels les valeurs du tableau généré par l’expression booléenne sont à ```True```.

__Note__ : L’expression booléenne génère un ```ndarray``` à 2 dimensions contenant des booléens, que l’on donne entre crochets à notre ```ndarray``` à 2 dimensions d’origine (Iris). Pourtant, en sortie, on obtient un ```ndarray``` à 1 dimension. Cela est dû au fait que certaines colonnes sont à False, ce qui déstructure totalement le ```ndarray```, et Python sort un tableau à une dimension contenant l’ensemble des valeurs étant à True : il ne peut pas faire autrement.

Appliquons une indéxation booléenne sur iris : 
```python
iris[iris > 2]
```
```
array([4.9, 3. , 4.7, 3.2, 4.6, 4. , 5. , 3.6, 5.4, 3.9, 4.6, 3.4, 5. ,
       3.4, 4.4, 2.9, 4.9, 3.1, 5.4, 3.7, 4.8, 3.4, 4.8, 3. , 4.3, 3. ,
       5.8, 4. , 5.7, 4.4, 5.4, 3.9, 5.1, 3.5, 5.7, 3.8, 5.1, 3.8, 5.4,
       ...
       ...
       6.9, 3.1, 5.1, 2.3, 3. , 5.8, 2.7, 5.1, 3. , 6.8, 3.2, 5.9, 2.3,
       3. , 6.7, 3.3, 5.7, 2.5, 3. , 6.7, 3. , 5.2, 2.3, 3. , 6.3, 2.5,
       5. , 3. , 6.5, 3. , 5.2, 3. , 6.2, 3.4, 5.4, 2.3, 3. , 5.9, 3. ,
       5.1, 3. ])
```
Ici, on obtient un tableau, toutes colonnes confondues, avec uniquement les valeurs supérieures à 2. Il n’y a plus de notions de colonnes, il s’agit d’un tableau à une dimension.

Sur ce tableau iris, __il n’y a pas vraiment d’intérêt à appliquer cette condition booléenne sur l’ensemble du tableau__. Mais, par exemple, la cinquième colonne correspond à l’espèce, donc en sélectionnant l’ensemble des valeurs supérieures à 2, on supprime d’office tous les individus d’Iris de l’espèce 1.

Pour appliquer la condition sur une colonne particulière du tableau, il faut la sélectionner en écrivant le masque booléen.

Syntaxe :
```python
mon_array[mon_array[:,index_colonne] == 2] 
```
Ici, on sélectionne la colonne en donnant sa position à droite de la virgule et on sélectionne l’ensemble des lignes de cette colonne en spécifiant le caractère ```:``` à gauche de la virgule (slicing).

Pour l’exemple, nous allons __sélectionner uniquement les valeurs où la longueur des sépales est supérieure à 5 centimètres__, c’est-à-dire où les valeurs de la première colonne sont supérieures à 5.
```python
iris[iris[:,0] > 5]
```
```
array([[5.4, 3.9, 1.7, 0.4, 1. ],
       [5.4, 3.7, 1.5, 0.2, 1. ],
       ...
       ...
       [6.2, 3.4, 5.4, 2.3, 3. ],
       [5.9, 3. , 5.1, 1.8, 3. ]])
```
Nous prenons le tableau ```iris``` et, entre crochets, nous écrivons notre condition : nous voulons que la première colonne (indice 0) soit supérieure à 5.

__Note__:
L’expression booléenne "```iris[:,0] >5```" génère un ```ndarray``` à 1 dimension contenant 150 valeurs (car il y a 150 lignes dans le tableau). Ainsi, Python sait qu’il doit garder uniquement les lignes à l’indice où la valeur est à True dans (iris[:,0] >5).

__Aperçu du tableau avant puis après l'indexation booléenne :__

![image](https://github.com/user-attachments/assets/ec2a4cf1-43c0-46fe-a455-adc6c385ddaf)


On constate que les lignes pour lesquelles la valeur de la première colonne est strictement supérieure à 5 sont présentes, mais les autres ne sont plus là.

### c. Fancy indexing
Consiste à donner un tableau d’indices (ou une liste d’indices) entre crochets à notre ndarray pour sélectionner plusieurs éléments non consécutifs. 

Alors qu’avec l’indexation simple on n’accède qu’à un seul élément, ici on peut en sélectionner autant qu’on veut. 
Ce qui est intéressant aussi, c’est que le format du tableau en sortie est le même que celui du tableau d’indices qu’on donne.

Syntaxe :
```python
mon_array[[5,2,8,4]]
```
On voit que l’ordre des indices peut ne pas être respecté, et qu’on donne autant d’indices qu’on veut. Ici, on va récupérer les valeurs du tableau ```mon_array``` aux indices ```5```, ```2```, ```8``` et ```4```, dans cet ordre. Cela génère un tableau à une dimension puisqu’on donne une unique liste de valeurs.

Pour générer un tableau à deux dimensions, on peut structurer manuellement les indices qu’on donne entre crochets.

Syntaxe :
```python
import numpy as np

# Ici, on crée un tableau à deux dimensions de type ndarray avec la fonction array() de NumPy.
# Ce tableau appelé array_indices, contient les indices
array_indices=np.array([[4,10,5],[12,8,9]])

# on donne ce tableau entre crochets à mon_array.
mon_array[array_indices]
# On obtient en sortie un tableau à deux dimensions (trois colonnes et deux lignes),
# avec une première ligne contenant les valeurs de mon_array aux indices 4, 10 et 5
# et une deuxième ligne contenant les valeurs de mon_array aux indices 12, 8 et 9.
```

Pour l’exemple, créons un tableau à une dimension contenant des nombres de 1 à 20. À partir de ce tableau à une dimension, créons un tableau à deux dimensions avec deux lignes et trois colonnes grâce au fancy indexing.
```python
import numpy as np
# créons un tableau à une dimension contenant des nombres de 1 à 20.
notre_tableau=np.array([1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20])
print("Contenu de notre_tableau :")
print(notre_tableau)
print("Nouveau tableau après fancy indexing :")
# À partir de ce tableau à une dimension, créons un tableau à deux dimensions
# avec deux lignes et trois colonnes grâce au fancy indexing.
print(notre_tableau[np.array([[4,10,5],[12,8,9]])])
```
```
Contenu de notre_tableau :
[ 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]
Nouveau tableau après fancy indexing :
[[ 5 11  6]
 [13  9 10]]
```
Il faut retenir que l’intérêt du fancy indexing est réellement de pouvoir sélectionner plusieurs valeurs dans un ordre quelconque, mais aussi de pouvoir structurer directement la sortie comme on le souhaite.

## 3. Accéder aux éléments par tranche (slicing)
Contrairement à l’indexation simple, qui utilise des indices simples et permet d’accéder à un seul élément, le slicing permet de sélectionner des tranches de tableaux (slices, en anglais) et donc de sélectionner plusieurs éléments du tableau. Avec le slicing, on récupérera ainsi un sous-ensemble du tableau.

syntaxe du slicing avec NumPy : :
```python
mon_array[start:stop:step] 
```
__start__
```start``` correspond à l’index auquel on souhaite commencer la sélection. Si elle n’est pas spécifiée, sa valeur par défaut est ```0```, soit le début du tableau
__stop__
```stop``` correspond à la valeur d’index à laquelle on veut arrêter la sélection, le numéro d’index donné n’étant pas compris dans la sélection. Exemple : si on donne l’index 5 comme valeur de ```stop```, Python sélectionnera les valeurs jusqu’à l’index 4 (l’index 5 n’étant pas inclus dans la sélection). Si elle n’est pas spécifiée, la valeur par défaut est le dernier index du tableau.
__step__
```step``` correspond au pas ; par défaut le pas est de 1.

### a. Slicing sur un tableau NumPy à 1 dimension
```python
import numpy as np
notre_tableau=np.array([1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17, 
18,19,20])
# On affiche les trois premiers éléments de ce tableau grâce au slicing. Les valeurs affichées sont celles aux index 0, 1 et 2.
notre_tableau[:3] # array([1, 2, 3])
```
```python
# À présent, on va afficher toutes les valeurs à partir de l’index 10 jusqu’à la fin du tableau.
notre_tableau[10:] # array([11, 12, 13, 14, 15, 16, 17, 18, 19, 20])
```
```python
# Maintenant, on va afficher les éléments des index 3 à 6. 
# Comme nous voulons afficher la valeur à l’index 6, nous spécifions 7 comme index stop, puisque Python n’inclut pas le stop dans sa sélection.
notre_tableau[3:7] # array([4, 5, 6, 7])
```
```python
# Si nous souhaitons afficher tous les éléments du tableau avec un pas de 2, cela est possible en spécifiant un step.
notre_tableau[::2] # array([ 1,  3,  5,  7,  9, 11, 13, 15, 17, 19])
```
```python

```
```python
```

### b. Slicing sur un tableau NumPy à 2 dimensions
Syntaxe :
```python
mon_array[start:stop:step, start:stop:step] # Comme pour l’indexing simple, à gauche la slice concerne les lignes, et à droite les colonnes.
```

```python
# Affichons les deux premières lignes et les quatre premières colonnes du tableau iris.
import numpy as np
iris=np.genfromtxt("C:/Users/chris/Documents/Travaux_personnels_2025/Python pour la Data Science/Jeux_de_donnees/iris.csv", skip_header=True, delimiter=";")
iris
```

__Aperçu du tableau iris :__
```
array([[4.9, 3. , 1.4, 0.2, 1. ],
       [4.7, 3.2, 1.3, 0.2, 1. ],
       [4.6, 3.1, 1.5, 0.2, 1. ],
       [5. , 3.6, 1.4, 0.2, 1. ],
       [5.4, 3.9, 1.7, 0.4, 1. ],
       [4.6, 3.4, 1.4, 0.3, 1. ],
       [5. , 3.4, 1.5, 0.2, 1. ],
       ...
```

__Affichons les deux premières lignes et les quatre premières colonnes du tableau iris.__
```python
iris[:2,:4]
```
```
array([[4.9, 3. , 1.4, 0.2],
       [4.7, 3.2, 1.3, 0.2]])
```

__Affichons les lignes à partir de l’index 145, jusqu’à la dernière ligne, et les colonnes à partir l’index 2, jusqu’à la dernière colonne.__

```python
iris[145:,2:]
```
```
array([[5. , 1.9, 3. ],
       [5.2, 2. , 3. ],
       [5.4, 2.3, 3. ],
       [5.1, 1.8, 3. ]])
```

__Pour afficher une ligne précise avec toutes ses colonnes, sans spécifier les colonnes à afficher, on peut mettre le symbole : à droite de la virgule, ce qui signifie "affiche-moi toutes les colonnes".__
```python
iris[0,:]
```

```
array([4.9, 3. , 1.4, 0.2, 1. ]) # La première ligne (et l’ensemble des colonnes) du tableau iris est affichée.
```

__Si on veut afficher toutes les lignes de la première colonne, nous mettrons cette fois-ci le symbole : à gauche de la virgule.__
```python
iris[:,0]
```
```
array([4.9, 4.7, 4.6, 5. , 5.4, 4.6, 5. , 4.4, 4.9, 5.4, 4.8, 4.8, 4.3,
       5.8, 5.7, 5.4, 5.1, 5.7, 5.1, 5.4, 5.1, 4.6, 5.1, 4.8, 5. , 5. ,
       5.2, 5.2, 4.7, 4.8, 5.4, 5.2, 5.5, 4.9, 5. , 5.5, 4.9, 4.4, 5.1,
       5. , 4.5, 4.4, 5. , 5.1, 4.8, 5.1, 4.6, 5.3, 5. , 7. , 6.4, 6.9,
       5.5, 6.5, 5.7, 6.3, 4.9, 6.6, 5.2, 5. , 5.9, 6. , 6.1, 5.6, 6.7,
       5.6, 5.8, 6.2, 5.6, 5.9, 6.1, 6.3, 6.1, 6.4, 6.6, 6.8, 6.7, 6. ,
       5.7, 5.5, 5.5, 5.8, 6. , 5.4, 6. , 6.7, 6.3, 5.6, 5.5, 5.5, 6.1,
       5.8, 5. , 5.6, 5.7, 5.7, 6.2, 5.1, 5.7, 6.3, 5.8, 7.1, 6.3, 6.5,
       7.6, 4.9, 7.3, 6.7, 7.2, 6.5, 6.4, 6.8, 5.7, 5.8, 6.4, 6.5, 7.7,
       7.7, 6. , 6.9, 5.6, 7.7, 6.3, 6.7, 7.2, 6.2, 6.1, 6.4, 7.2, 7.4,
       7.9, 6.4, 6.3, 6.1, 7.7, 6.3, 6.4, 6. , 6.9, 6.7, 6.9, 5.8, 6.8,
       6.7, 6.7, 6.3, 6.5, 6.2, 5.9])
```

__On peut aussi utiliser des chiffres négatifs, pour réfléchir à l’envers et afficher le tableau à partir de la fin.__
```python
iris[-1,:] # array([5.9, 3. , 5.1, 1.8, 3. ]) # La dernière ligne du tableau est affichée.
```
Le but du __slicing__ est vraiment d’afficher un sous-tableau d’intérêt à partir d’un grand tableau.

## 4. Notion de vue et copie
Lorsqu’on fait du slicing sur un tableau, ce qu’il retourne, c’est une vue du tableau et non pas une copie du tableau.

Ainsi, une modification de ```sous_tableau``` entraîne la modification du tableau initial (tableau de base). Quand on fait une extraction de type __slicing__, on crée une vue de ```tableau initial``` qu’on range dans ```sous_tableau```.

```sous_tableau``` n’est pas un nouvel ```ndarray```, mais bien une vue du ```ndarray``` tableau initial (tableau de base).

__Note__
Les slices de liste, par exemple, sont bien des copies de la liste originale, c’est-à-dire que si on modifie la sous-liste, la liste initiale n’est pas modifiée. La notion de vue et copie est réellement spécifique à la librairie NumPy.

Vous vous demandez sûrement la raison pour laquelle NumPy crée une vue par défaut. En fait, NumPy a été développée pour travailler sur de très gros tableaux et pour être très performante en calcul scientifique. Ainsi, il faut savoir que créer une copie prend deux fois plus de temps que de créer une vue, mais aussi que quand on crée une copie du tableau, cela prend de la mémoire supplémentaire, alors que la vue partage le même espace mémoire (sur votre ordinateur) que le tableau original. Étant donné que la mémoire est souvent ce qui est limitant dans le cas de gros calculs, cet avantage des vues n’est pas négligeable.

Si toutefois vous voulez vraiment travailler sur une copie du tableau original, c’est-à-dire sur un sous-ensemble du tableau original sans modifier l’original, vous pouvez explicitement créer une copie.

```python
import numpy as pd

notre_tableau=np.array([1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20])
sous_tableau=notre_tableau[:5].copy()

sous_tableau[0]=10

print(sous_tableau)

print(notre_tableau)
```
```
[10  2  3  4  5]
[ 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]
```
