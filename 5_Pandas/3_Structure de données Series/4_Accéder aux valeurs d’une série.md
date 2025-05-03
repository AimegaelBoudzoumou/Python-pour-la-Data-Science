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

Ce code nous permet d’accéder à l’information de poids de ces deux athlètes qui font respectivement 96 et 89 kg.

L’indexing avec les positions des valeurs ou leurs étiquettes, entre crochets [], est très répandu mais peut être à l’origine d’erreurs de mauvaise sélection de données. Pour que ces erreurs n’arrivent pas, les attributs .loc et .iloc ont été mis en place.

## c. Les indexeurs loc et iloc
Pandas propose deux indexeurs pour spécifier à Python si nous souhaitons effectuer l’indexing sur les étiquettes d’index ou sur les positions des valeurs dans la série : ce sont les indexeurs loc et iloc. Ces indexeurs peuvent être considérés comme des attributs des objets de classe Series et DataFrame.

Syntaxe:
```python
serie.loc[etiquette] 
serie.iloc[position]
```

Les attributs sont suivis des étiquettes ou positions auxquelles on souhaite récupérer des valeurs, entre crochets ```[]```.

__Pratiquons__
ON va créer une série nommée ```ma_serie```, qui contient quatre valeurs et dont les noms d'index sont respectivement 1,3,2 et 0.
```python
import pandas as pd
ma_serie = pd.Series([10,11,12,13], [1,3,2,0])
print(ma_serie)
```
![image](https://github.com/user-attachments/assets/d5687999-7951-4706-a97f-05d222ddc0be)

### loc

L’attribut loc va demander à Pandas d’utiliser les noms d’index, les étiquettes, pour sélectionner les valeurs dans la série.

```python
ma_serie.loc[0] # affichera 13
```

L’attribut loc retourne la valeur dont le nom de l’index est 0.

### iloc

L’attribut iloc va demander à Pandas d’utiliser la position des valeurs pour les sélectionner dans la série.

```python
ma_serie.iloc[0] # affichera 10
```

## d. Indexing via une expression booléenne
Enfin, il est possible de faire de l’indexing en utilisant une expression booléenne. Ici, cet indexing ne se base plus sur les positions ou les étiquettes des valeurs, __mais réellement sur les valeurs de la série__. 

Par exemple, si on veut récupérer l’ensemble des valeurs strictement supérieures à ```10``` dans la série, la syntaxe est la suivante :

```python
ma_serie[ma_serie>10]
```

Ainsi, il s’agit d’utiliser les opérateurs de comparaisons (<, <=, >, >=, ==, !=) pour effectuer l’indexing.

__Pratiquons__
Illustrons cela avec un exemple. Sélectionnons uniquement les athlètes avec un poids strictement supérieur à 90 kg.
```python

```


## e. Slicing : découpage de valeurs successives
