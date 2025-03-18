# Les différents types de données (int, float, bool, str)

## 1. Les nombres réels et entiers
Le type de données ou le type d’une variable indique à l’interpréteur Python ce qu’il peut faire ou ne pas faire avec cette variable.

Par exemple, précédemment, nous manipulions des chiffres ou nombres entiers, c’est ce qu’on appelle le type ```int``` pour integer (entier, en français). La fonction ```type()```  permet d’afficher le type d’une valeur.

```python
type(11) # int
```

Si nous mettons une virgule à la valeur, on obtient un nombre réel (un nombre à virgule) et le type sera ```float```.


```python
type(11.1) # float
```

Il existe donc deux types de nombres en Python ; les nombres réels (```float```) et les nombres entiers (```int```).

Il est possible de transformer un integer en float et vice versa, grâce aux fonctions ```int()``` et ```float()```.

```python
int(3.5) # 3

float(3) # 3.0
```

## 2. Les booléens
Les booléens résultent d’opérations logiques et ont deux valeurs possibles : TRUE ou FALSE, soit VRAI ou FAUX. Plus simplement, ce type de données permet de savoir si une condition est vraie ou fausse.

```python
3 < 5 # True

3 > 5 # False
```

Ici, le premier code demande à Python si 3 est inférieur à 5 et il renvoie True, donc "vrai". Ensuite, on lui demande si 3 est supérieur à 5 et il répond False, donc "faux".

C’est ce qu’on appelle des opérateurs de comparaison, qui vont retourner des booléens selon que le résultat est vrai ou faux.

Pour afficher le type de 3 > 5, on utilisera le code suivant :
```python
type(3>5) # bool
```

