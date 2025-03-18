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
Les booléens résultent d’opérations logiques et ont deux valeurs possibles : ```TRUE``` ou ```FALSE```, soit VRAI ou FAUX. Plus simplement, ce type de données permet de savoir si une condition est vraie ou fausse.

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

## 3. Les chaînes de caractères
Le type "chaîne de caractères" permet d’écrire une suite finie de caractères, qu’on peut aussi définir comme du texte. Pour créer une chaîne de caractères, il faut mettre du texte entre doubles guillemets ou simples guillemets.

```python
"mon texte"

print("mon texte") # mon texte
```

```python
type("mon texte") # str
```

str signifie string en anglais, ou encore phrase en français.

Un nombre peut aussi être considéré comme du texte, s’il est mis entre guillemets.

```python
type("15") # str
```

Mais il ne se comporte plus comme un nombre ici.

Par exemple, avec deux nombres, on peut utiliser Python comme une calculatrice et les additionner.
```python
5 + 15 # 20
```

En revanche, on ne peut plus additionner la chaîne de caractères "15" avec un nombre comme précédemment, car il n’est plus considéré comme un nombre, mais bien comme du texte.
```python
"15" + 2 # TypeError: can only concatenate str (not "int") to str
```

On obtient une erreur, car on ne peut pas additionner du texte et un nombre.

Enfin, si on veut transformer un nombre en chaîne de caractères, on utilisera la fonction ```str()```.

```python
str(15) # '15'

type(str(15)) # str
```

Exercices pratiques : voir les fonctions 

