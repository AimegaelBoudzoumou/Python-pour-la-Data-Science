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

```

## b. Indexing via l’étiquette des valeurs

## c. Les indexeurs loc et iloc

## d. Indexing via une expression booléenne

## e. Slicing : découpage de valeurs successives
