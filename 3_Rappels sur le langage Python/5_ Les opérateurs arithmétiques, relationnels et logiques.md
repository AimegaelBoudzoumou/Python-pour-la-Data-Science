# Les opérateurs arithmétiques, relationnels et logiques

## 1. Les opérateurs arithmétiques
Python peut se comporter comme une calculatrice grâce aux opérateurs arithmétiques que l’on connaît bien : l’addition, la soustraction, la multiplication, la division.

```python
# Une addition 
print("Résultat de l'addition 5+3 :") 
print(5+3) # 8
# Une soustraction 
print("Résultat de la soustraction 5-3 :") 
print(5-3) # 2
# Une division 
print("Résultat de la division 10/3 :") 
print(10/3) # 3.3333333333333335
print("Le reste de la division 10/3 :") 
print(10 % 3) # 1
```



## 2. Les opérateurs relationnels et logiques

### a. Les opérateurs relationnels
Les opérateurs relationnels sont aussi appelés opérateurs de comparaison, car ils permettent de comparer des expressions. Ils sont fréquemment utilisés en Data Science lorsqu’on explore des données.

Voici les opérateurs relationnels.

Il y a l’opérateur ```==```, qui permet de comparer deux valeurs, afin de tester si elles sont égales ou non. Il y a aussi l’opérateur ```!=```, qui est le contraire de ```==``` et permet de tester si deux valeurs sont différentes.

Attention : ne confondez pas l’opérateur d’assignation = avec l’opérateur de comparaison ==.

Ces comparaisons renvoient un type de données que nous avons vu précédemment ensemble : le booléen. Si la comparaison est vraie, la valeur True est renvoyée, si elle est fausse, la valeur False est renvoyée.

```python
print(1==1) # True
print(1!=1) # False
print(5>3) # True
print(10>=10) # True
print(3>25) # False
```

### b. Les opérateurs logiques
Les opérateurs logiques permettent de comparer des expressions booléennes, et non plus des valeurs en tant que telles. Globalement, les opérateurs logiques sont associés aux opérateurs relationnels pour écrire des expressions de comparaisons plus complexes.

Syntaxe générale avec __and__:
```python
(valeur == valeur2) and (valeur3 != valeur4) 
```
Il y a deux opérateurs logiques, ```and``` (qui signifie et) et ```or``` (qui signifie ou). Dans l’expression écrite ci-dessus, la valeur ```True``` sera renvoyée si et seulement si ```valeur``` est égale à ```valeur2``` __ET__ si ```valeur3``` est différente de ```valeur4```.

Syntaxe générale avec __or__:
```python
(valeur == valeur2) or (valeur3 != valeur4) 
```
Ici, si une des comparaisons seulement est vraie, alors cette expression renvoie ```True```. Avec le ```or```, il n’est pas nécessaire que les deux comparaisons soient vraies, contrairement au ```and```.

```python
print((3 ==3) and (4 == 4)) # True 
print((3 ==3) and (4 == 5)) # False
print((3 ==3) or (4 == 5)) # True
```

__not__

Si vous souhaitez le contraire de l’expression que vous énoncez, par exemple, si vous souhaitez que lorsque le résultat de votre expression booléenne est ```False```, Python vous renvoie ```True```, alors vous utiliserez le dernier opérateur logique, qui est ```not```, pour "non" ou "pas" en français. 

```python
not((3 ==4) or (4 == 5)) # True
```

__bitwise__

Ici nous utilisons les opérateurs logiques car chaque expression booléenne génère une unique valeur True ou False. Par exemple, ````3==3``` génère ```True``` et ```4==4``` génère ```True``` aussi, donc les opérateurs logiques fonctionnent. Nous verrons dans le chapitre sur la librairie Pandas, notamment, que lorsque les expressions booléennes renvoient des objets contenant plusieurs booléens, nous utilisons les opérateurs ```bitwise``` (comparaison bit à bit), plutôt que les opérateurs logiques.
