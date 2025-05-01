# Lecture de fichiers texte (CSV ou TXT)

### a. Lecture basique d’un fichier
### b. Gestion de l’en-tête
### c. Gestion des index
### d. Création d’un tableau à une dimension à partir du fichier
### e. Filtrage des colonnes lors de la lecture du fichier
### f. Les types des différentes colonnes
### g. Gestion des dates lors de la lecture du fichier

-----------------------------------------------------------------------------------------------------------------------------------------------------------------

## a. Lecture basique d’un fichier

Lorsqu’on souhaite utiliser Pandas pour analyser des données, la première étape est généralement d’importer les données dans son notebook. Les fichiers peuvent être de différents formats, mais le plus courant en Data Science est le format CSV. CSV signifie comma-separated values, traduisez : "valeurs séparées par une virgule". 

Il s’agit donc d’un format texte, dans lequel les colonnes sont séparées par des virgules. L’autre format très courant est le format TXT, qui lui aussi est un format texte, mais contenant des valeurs séparées par des tabulations, cette fois.

### read_table()

Pour lire un fichier TXT avec Pandas, il faut utiliser la fonction ```read_table()```, dont la syntaxe générale est la suivante :

__Syntaxe :__
```python
import pandas as pd 
pd.read_table("mon_fichier.txt")
```

### read_csv()

Pour lire un fichier CSV avec Pandas, il faut utiliser la fonction ```read_csv()```, dont la syntaxe générale est la suivante :

__Syntaxe :__
```python
import pandas as pd 
pd.read_csv("mon_fichier.csv")
```

La fonction read_table() peut s’adapter à tout type de séparateur, que ce soit le point-virgule (;), l’espace (" "), etc., 
et il en va de même pour la fonction read_csv(). 

```python
import pandas as pd 
pd.read_table("mon_fichier.csv", sep=",")
```

Il est simplement logique d’utiliser la fonction read_table() pour des fichiers TXT et la fonction read_csv() pour des fichiers CSV.

À présent, importons notre jeu de données exemple dans notre notebook, avec la commande suivante :

```python
import pandas as pd
donnees=pd.read_csv(r"Python Data Science\JO_Dataset\athlete_events.csv")
donnees.head()
```

__Note :__

__DataFrame__ : tableau à deux dimensions

__Series__ : tableau à une dimension


### b. Gestion de l’en-tête

#### header
La première option importante est la notion de header, que l’on peut traduire par "en-tête" en français. Il s’agit plus simplement des noms de colonnes. Par défaut, Python prendra la première ligne du fichier comme en-tête du tableau, ce qui fonctionne bien dans le cas de notre jeu de données, où la première ligne correspond effectivement aux noms des variables.

Toutefois, si votre tableau ne contient pas de header, et que vous ne voulez pas qu’il y en ait, vous pouvez le spécifier avec la syntaxe suivante :Toutefois, si votre tableau ne contient pas de header, et que vous ne voulez pas qu’il y en ait, vous pouvez le spécifier avec la syntaxe suivante :

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv", header=None)
```

Ici, les noms de colonnes correspondront à des valeurs partant de 0 et qui s’incrémentent de 1 en 1 (0, 1, 2, 3, etc.).

#### skiprows
Elle permet d’ignorer certaines lignes lors de la lecture du fichier et elle ne les stocke pas dans le tableau. Par exemple, si on veut supprimer l’en-tête du fichier lors de la lecture, on donnera la valeur "1" à l’option skiprows pour ignorer la première ligne du fichier.

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv", skiprows=1, header=None)
```

#### names
Si votre fichier ne possède pas d’en-tête, mais que vous voulez en créer un lors de la lecture du fichier, vous pouvez le faire avec l’option names. La syntaxe est la suivante :

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv", names=['colonne_1','colonne_2'])
```

Ici, vous n’avez pas besoin de spécifier que votre fichier ne contient pas de header avec l’option ```header=None```, car comme vous passez l’option ```names``` à la fonction ```read_csv()```, Pandas comprend qu’il ne doit pas prendre le header dans votre fichier, mais qu’il doit le définir avec la liste que vous lui donnez dans l’option ```names```.

Imaginons que nous souhaitions supprimer l’en-tête en anglais de notre fichier et que nous voulions en mettre un nouveau, en français.

```python
import pandas as pd 
donnees_francais=pd.read_csv(r"Python Data Science\JO_Dataset\athlete_events.csv",skiprows=1, names=["Id","Nom", 
"Sexe", "Age", "Taille", "Poids", "Equipe", "CNO", "Jeux",  
"Annee", "Saison", "Ville", "Sport", "Epreuve", "Medaille"]) 
donnees_francais.head()
```

![image](https://github.com/user-attachments/assets/c6ab116a-7db5-4b05-93a0-8efedb679387)


## c. Gestion des index
Il y a différentes manières de gérer les index lors de la lecture d’un fichier. Celui-ci peut être implicite si on a une entrée en moins dans le header par rapport au nombre de colonnes, c’est-à-dire si le nom de la première colonne est vide. Dans ce cas, la fonction ```read_csv()``` (ou ```read_table()```) prend par défaut la première colonne comme étant l’index.

Il est aussi possible de spécifier quelle colonne du jeu de données correspond à l’index, grâce à l’option index_col. Ici, Pandas définit la première colonne du fichier comme étant l’index du tableau.

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv", index_col=0)
```

Enfin, il est possible de définir plusieurs colonnes comme étant les index, toujours grâce à l’option index_col. Ici, la première et la deuxième colonne deviennent les index du tableau après lecture du fichier.

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv", index_col=[0,1]) 
```

#### Définir un index pour notre jeux de données
Lorsqu’on regarde notre tableau donnees, on constate qu’il y a une colonne ```ID``` qui correspond à l’identifiant de chaque athlète, on pourrait vouloir le définir comme index.

```python
import pandas as pd
donnees_1index=pd.read_csv(r"Python Data Science\JO_Dataset\athlete_events.csv", index_col=[0])
donnees_1index.head()
```

![image](https://github.com/user-attachments/assets/6ec35537-342d-4af5-975c-6fe0c411b550)

Ici, on constate que la colonne ID du fichier est devenue l’index du tableau. Avec Pandas et ses structures, il est possible d’avoir des index qui ne sont pas uniques. Ainsi, si un athlète est présent plusieurs fois dans le fichier, son ID sera lui aussi présent plusieurs fois dans l’index. Et cela permet de faire des traitements particuliers avec Pandas sur les index.

## d. Création d’un tableau à une dimension à partir du fichier

#### squeeze
Pour rappel, il existe deux structures de données que nous verrons juste après, correspondant à un tableau à une dimension (```Series```) ou un tableau à deux dimensions (```DataFrame```). 
Les fonctions de lecture de fichiers de Pandas créeront par défaut un dataframe, même à partir d’un fichier ne contenant qu’une seule colonne, et qui pourrait donc être stockée comme une série. Si on souhaite créer un tableau à une dimension plutôt que deux, il faudra spécifier l’option ```squeeze```.

```python
import pandas as pd 
pd.read_csv("fichier.csv", squeeze=True)
```

## e. Filtrage des colonnes lors de la lecture du fichier

#### usecols

Il est possible, dès la lecture du fichier, de ne lire que certaines colonnes du tableau si toutes ne nous intéressent pas, grâce à l’option usecols.

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv", usecols=[3,6])
```

Ici, on demande de n’importer que les colonnes 4 et 7 du fichier.

Il est aussi possible de sélectionner des colonnes en donnant une liste de noms de colonnes plutôt qu’une liste de positions de colonnes.

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv",usecols=["macolonne_1",macolonne_2"])
```

Passons à l’exemple pratique. Si on ne souhaite sélectionner que les colonnes contenant les noms des athlètes, leur poids et leur taille, le code sera le suivant.

```python
import pandas as pd
donnees_usecols_position=pd.read_csv(r"Python Data Science\JO_Dataset\athlete_events.csv", usecols=[1,4,5])
donnees_usecols_position.head()
```

Dans le code précédent, nous sélectionnons les colonnes grâce à leurs positions. Dans le code suivant, sélectionnons les colonnes par leurs noms plutôt que leurs positions.

```python
import pandas as pd
donnees_usecols_position=pd.read_csv(r"Python Data Science\JO_Dataset\athlete_events.csv", usecols=[1,4,5])
donnees_usecols_position.head()
```

Dans les deux cas, les premières lignes de la sortie sont les suivantes.

![image](https://github.com/user-attachments/assets/0180effd-3393-475b-8cb1-4811abbf2e33)

## f. Les types des différentes colonnes

Il est possible de spécifier le type de chaque colonne afin que Pandas prenne en compte les différents traitements possibles qu’il peut faire sur chaque colonne. En effet, on ne peut pas faire les mêmes traitements sur une colonne de type numérique que sur une colonne de type caractère. Par exemple, on peut multiplier une colonne de type numérique, mais pas une colonne de type caractère.

La syntaxe générale pour spécifier le type des colonnes est la suivante :

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv",dtype={"macolonne_1":"Int64", 
"macolonne_2":"float64", "macolonne_3":"object"})
```

Ici, il suffit de donner un dictionnaire avec en clé les noms de colonnes et en valeurs le ```dtype``` de cette colonne.

## g. Gestion des dates lors de la lecture du fichier
Enfin, certaines colonnes peuvent contenir des dates et il est important de les parser correctement. Parser pourrait être traduit par "analyser la syntaxe d’un texte". Pandas va analyser le format de la date et la formater correctement.

Lors de la lecture du fichier, on peut spécifier quelles colonnes traiter comme des dates. Par exemple, si la colonne 5 de notre fichier contient des dates, on le dit lors de la lecture.

```python
import pandas as pd 
pd.read_csv("mon_fichier.csv",parse_dates=[4])
```

Lorsque nous visualiserons notre tableau, nous pourrons constater que le ```dtype``` de notre colonne est ```datetime64```.

__Pratiquons :__
On sait que la colonne 9 de notre dataframe correspond à l’année des Jeux olympiques auxquels ont participé les athlètes. On pourrait vouloir dire à Pandas de considérer cette colonne comme une date.

````python
donnees.dtypes
```

Pour l’instant, si on regarde le type de la colonne 9, on a le résultat suivant.

```python
Year        int64
```

Ici, notre colonne représentant l’année des JO est considérée comme un type entier par Pandas. En précisant que la colonne 9 doit être considérée comme une date, on obtient le résultat suivant.

```python
import pandas as pd
donnees=pd.read_csv(r"Python Data Science\JO_Dataset\athlete_events.csv", parse_dates=[9])
donnees.head()
```

![image](https://github.com/user-attachments/assets/6eea1d04-1ddf-44a6-97f4-2204eb4b0f56)

```python
donnees.dtypes
```

```python
Year      datetime64[ns]
```

La colonne 9 est bien de type datetime64 maintenant.
