# Accéder aux valeurs d’une série

#### a. Indexing via la position des valeurs

#### b. Indexing via l’étiquette des valeurs

#### c. Les indexeurs loc et iloc

#### d. Indexing via une expression booléenne

#### e. Slicing : découpage de valeurs successives

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## a. Indexing via la position des valeurs

Lorsqu’on souhaite sélectionner une ou des valeurs dans une série, on va chercher à sélectionner des données à des positions particulières.

Par exemple, si on souhaite récupérer la valeur en position 2 dans l’objet ma_serie, la syntaxe est :
```python
ma_serie[1]
```

Pour sélectionner plusieurs valeurs, il suffit de donner une liste de positions, d’index, entre crochets, avec la syntaxe suivante :
```python
ma_serie[[1,5,9]]
```

Ici, le premier couple de crochets ```[1,5,9]``` permet de créer la liste de valeurs et le deuxième couple de crochets ```[ ]``` permet d’effectuer l’indexing sur l’objet ```ma_serie```.

Il est aussi possible d’utiliser des valeurs négatives. Par exemple, ```-1``` signifie "la dernière valeur de la série", ```-2``` signifie "l’avant-dernière valeur de la série", etc.
```python
ma_serie[-1] 
```

__Pratiquons__
Pour récupérer plusieurs valeurs à plusieurs positions, il suffit de donner une liste de ces positions entre crochets. Récupérons les valeurs de poids des athlètes aux positions 0, 15, 6985 et 452.

```python
import pandas as pd
ma_serie_de_poids_index_defaut=pd.read_csv("athlete_events.csv", usecols=[5])
ma_serie_de_poids_index_defaut = ma_serie_de_poids_index_defaut.squeeze()
ma_serie_de_poids_index_defaut[[0, 15,6985,452]]
```

Le premier couple de crochets ```ma_serie_de_poids_index_defaut[]``` correspond à la syntaxe pour sélectionner des données et le deuxième couple de crochets ```[0,15,6985,452]``` correspond à la liste des positions auxquelles on souhaite récupérer des valeurs.

![image](https://github.com/user-attachments/assets/4f12d83d-b368-4393-9599-bccf3c27cbca)

Nous venons de récupérer les valeurs aux positions 0, 15, 6985 et 452.

## b. Indexing via l’étiquette des valeurs
Il est aussi possible de sélectionner des valeurs selon l’étiquette de ces valeurs. Par exemple, imaginons que nous voulons sélectionner la valeur dont l’étiquette est la chaîne de caractères "```ma_valeur```". La syntaxe sera la suivante :

```python
ma_serie["ma_valeur"]
```

Pour sélectionner plusieurs valeurs :

```python
ma_serie[["ma_valeur1", "ma_valeur2","ma_valeur3"]] 
```

__Pratiquons__

<!--
Pour l’exemple de cette sous-section, nous allons repartir sur la série que nous avons créée précédemment et sur laquelle nous avons redéfini les index avec les noms des athlètes : ma_serie_de_poids.
-->

```python
import pandas as pd
ma_serie_de_poids=pd.read_csv("athlete_events.csv", usecols=["Weight", "Name"], index_col=["Name"])
ma_serie_de_poids = ma_serie_de_poids.squeeze()
ma_serie_de_poids[["Tomasz Ireneusz ya", "Christine Jacoba Aaftink"]]
```

![image](https://github.com/user-attachments/assets/436c13bb-f4f7-4ae6-9a0c-5c449fd580b9)

```python
import pandas as pd
ma_serie_de_poids=pd.read_csv("athlete_events.csv", usecols=["Weight", "Name"], index_col=["Name"])
ma_serie_de_poids = ma_serie_de_poids.squeeze()
ma_serie_de_poids[["Antti Sami Aalto", "Andrzej ya"]]
```

![image](https://github.com/user-attachments/assets/4a5a4a9d-3913-497c-af36-f77cf6ca7582)




## c. Les indexeurs loc et iloc

## d. Indexing via une expression booléenne

## e. Slicing : découpage de valeurs successives
