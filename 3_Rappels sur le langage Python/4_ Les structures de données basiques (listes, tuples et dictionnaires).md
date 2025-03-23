# Les structures de données basiques (listes, tuples et dictionnaires)

## 1. Les listes
Une liste est un nouveau type de variable, qui permet de stocker plusieurs éléments, plusieurs valeurs, qui sont ordonnés, modifiables et peuvent être de type différent (```int```, ```float```, ```str``` ou ```bool```). 

Ainsi, on peut avoir une liste contenant uniquement des nombres entiers, uniquement des nombres réels, uniquement des chaînes de caractères, uniquement des booléens ou encore les quatre mélangés. De plus, une liste peut contenir elle-même des listes.

### a. Créer une liste

Syntaxe:
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
print(type(ma_liste)) # <class 'list'>
print(ma_liste) # [1, 2, 3, 4, 5, 6, 7, 8, 'hello', 10.5]
```

### b. Accéder aux éléments d’une liste
Pour afficher une valeur particulière d’une liste, on donnera l’index (indice) auquel se trouve la valeur qu’on souhaite afficher, c’est-à-dire la position de la valeur dans la liste.

Note : Python commence à compter à partir de ```0```. Donc pour afficher la première valeur de la liste, il faut donner l’index ```0```, pour afficher la deuxième valeur de la liste, il faut donner l’index ```1```, etc.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
print(ma_liste[1]) # 2
```

Plutôt que de donner un seul index, Python permet d’effectuer du slicing sur les listes, c’est-à-dire du découpage en français.

Syntaxe:
```
ma_liste[start:stop:step]
```

Ici, plutôt que d’accéder aux valeurs une par une grâce à l’indexage simple (où on ne donne qu’un index), on va donner l’index de départ, l’index de fin et le pas (par défaut le pas est de 1, si on met 2, par exemple, Python saute une valeur sur 2).

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[2:4] # [3, 4]
```

Python retourne une liste contenant les valeurs des index ```2``` et ```3```, c’est-à-dire les valeurs ```3``` et ```4``` de ```ma_liste```. Instinctivement, on pourrait penser qu’en écrivant ```2:4```, Python donnerait les valeurs aux index ```2```, ```3``` et ```4```, mais non, il donne les valeurs jusqu’à l’index ```n-1```.

Si on ne donne pas d’index au début, Python part du début de la liste.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[:4] # [1, 2, 3, 4]
```

Python affiche ```1```, ```2```, ```3``` et ```4```, les valeurs des index ```0```, ```1```, ```2```, ```3```.

Si on ne met rien comme dernier index, Python affichera la liste à partir de l’index qu’on lui donne jusqu’à la fin de la liste.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[3:] # [4, 5, 6, 7, 8, 'hello', 10.5]
```

On peut aussi donner une valeur de début, une valeur de fin et une valeur de pas. Le pas est de 1 par défaut, mais si nous le mettons à 2, Python saute une valeur sur deux.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[0:3:2] # [1, 3]
```

Voici quelques astuces de slicing supplémentaires.

Afficher les valeurs des index pairs, en partant de l’index 0 (premier index pair) jusqu’à la fin de la liste, avec un pas de 2.

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[::2] # [1, 3, 5, 7, 'hello']
```

Afficher les valeurs des index impairs, en partant de l’index 1 (premier index impair) jusqu’à la fin de la liste, avec un pas de 2.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[1::2] # [2, 4, 6, 8, 10.5]
```

Si on souhaite partir de la fin de la liste, il suffit d’utiliser des nombres négatifs.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[-2] # 'hello'
```

Enfin, on peut aussi partir d’un entier positif pour arriver jusqu’à un entier négatif. 
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[1:-4] # [2, 3, 4, 5, 6]
```

### c. Ajouter et supprimer des éléments à une liste
La liste est une structure modifiable, on peut donc ajouter, supprimer et modifier les valeurs de la liste.

__Ajout__
La méthode ```append()``` permet d’ajouter des éléments à une liste.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste.append(2)
print(ma_liste) # [1, 2, 3, 4, 5, 6, 7, 8, 'hello', 10.5, 2]
```

La méthode ```append()``` ajoute l’élément en fin de liste. Si on souhaite ajouter un élément à un endroit précis de la liste, on utilise la méthode ```insert()```, qui signifie insérer en français.

Ajoutons la chaîne de caractères "```nouvelle```" à la position 5, l’index 5 de ```ma_liste```.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste.insert(5,"nouvelle")
print(ma_liste) # [1, 2, 3, 4, 5, 'nouvelle', 6, 7, 8, 'hello', 10.5]
```

On voit bien que la chaîne de caractères a été insérée à la position 5, en comptant à partir de 0, toujours.

__Modification__

Pour modifier un élément, on peut se servir de l’indexage simple, avec un index entre crochets, ou du slicing. Puis on attribue une (ou des) nouvelle(s) valeur(s) à la position (ou aux positions) donnée(s).

Sytaxe:
```python
ma_liste[index]=nouvelle_valeur 
ma_liste[start:stop:step]=[liste de nouvelles valeurs]
```

```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[0] = "a"
print(ma_liste) # ['a', 2, 3, 4, 5, 6, 7, 8, 'hello', 10.5]
```

Ici, Python met la valeur ```8``` à l’index ```3``` et la valeur ```10``` à l’index ```4```.
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
print(ma_liste) # [1, 2, 3, 4, 5, 6, 7, 8, 'hello', 10.5]
ma_liste[3:5]=[8,10]
print(ma_liste) # [1, 2, 3, 8, 10, 6, 7, 8, 'hello', 10.5]
```

__Suppression__
Pour supprimer des valeurs avec le slicing, c’est le même principe que la modification : on donne les index auxquels on veut supprimer les valeurs et on donne une liste vide.

Syntaxe:
```python
ma_liste[start:stop:step] = []
```

Imaginons que l’on veuille supprimer les valeurs aux index 0 et 1 :
```python
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[0:2] = []
print(ma_liste) # [3, 4, 5, 6, 7, 8, 'hello', 10.5]
```

Une liste peut liste une autre liste:
```pyton
ma_liste = [1,2,3,4,5,6,7,8,"hello" ,10.5]
ma_liste[3] = []
print(ma_liste) # [1, 2, 3, [], 5, 6, 7, 8, 'hello', 10.5]
```

Pour réussir à supprimer un seul élément avec l’indexage simple (un seul index entre crochets), on peut utiliser le mot-clé ```del```.

```del``` prend en entrée un argument et le supprime.

Syntaxe:
```python
del ma_liste[mon_index]
```

Supprimons la valeur à l’index 3 de ma_liste.
```python
print(ma_liste) # [1, 2, 3, [], 5, 6, 7, 8, 'hello', 10.5]
del ma_liste[3]
print(ma_liste) # [1, 2, 3, 5, 6, 7, 8, 'hello', 10.5]
```
La liste vide précédemment ajoutée a bien été supprimée de ma_liste.

## 2. Les tuples
Un tuple n’est rien d’autre qu’une liste, à la seule différence que le tuple est une liste qu’on ne peut pas modifier. Pour créer un tuple, cela se fait de la même manière que pour une liste, sauf que les crochets sont remplacés par des parenthèses.

```python
mon_tuple=(1,2,3,4,5)
print(type(mon_tuple)) # <class 'tuple'>
print(mon_tuple) # (1, 2, 3, 4, 5)
```

Pour accéder à un élément d’un tuple, on utilise l’indexage simple, comme pour les listes.
```python
mon_tuple[0] # 1
```

Deux avantages des tuples : l’assignation multiple et la protection en écriture.

Assignation multiple grâce aux tuples.
```python
ma_variable1, ma_variable2 = 1, 2
print(ma_variable1) # 1
print(ma_variable2) # 2
```

On ne peut pas ajouter, supprimer ou modifier des éléments.
```python
mon_tuple[0]=10
print(mon_tuple) # TypeError: 'tuple' object does not support item assignment
```
Lorsque nous souhaitons que des données restent inchangées dans notre programme, nous les assignons à un tuple, ce qui garantit leur protection et leur non-modification.

## 3. Les dictionnaires

### a. Introduction aux dictionnaires

Un dictionnaire est une structure qui n’est pas ordonnée (contrairement aux listes), qui peut être modifiée et qui est indexée, tout comme les listes. Il est aussi possible de mélanger les types de valeurs dans un dictionnaire (caractères, entiers...).

Le principe des dictionnaires est de lier une clé à une valeur et de pouvoir accéder aux valeurs grâce à ces clés. Ainsi, plutôt que de travailler avec des numéros d’index pour accéder à nos valeurs, nous pouvons travailler avec des clés, des mots.

Pour créer un dictionnaire, on utilise les accolades {}, puis on donne un ensemble de couples clé-valeur, séparés par une virgule.

```python
notes_eleves = {
    "Marie": 15, 
    "Thomas": 12, 
    "Julien": "absent", 
    "Elise": 9, 
    "Samuel": 17 
}
print(notes_eleves) # {'Marie': 15, 'Thomas': 12, 'Julien': 'absent', 'Elise': 9, 'Samuel': 17}
```

Afficher une valeur grâce à sa clé:
```python
notes_eleves["Samuel"] # 17
```

### b. Ajouter, modifier et supprimer des éléments d’un dictionnaire

__Ajout__

On peut ajouter un nouveau couple clé-valeur dans un dictionnaire existant.

```python
notes_eleves["Julie"]=9
print(notes_eleves) # {'Marie': 15, 'Thomas': 12, 'Julien': 'absent', 'Elise': 9, 'Samuel': 17, 'Julie': 9}
```

__Modification__
Pour modifier une valeur, il faut dire à Python pour quelle clé il doit modifier la valeur associée.

```python
notes_eleves["Julien"]=13
print(notes_eleves) # {'Marie': 15, 'Thomas': 12, 'Julien': 13, 'Elise': 9, 'Samuel': 17, 'Julie': 9}
```

Attention : Attention : un dictionnaire ne peut pas contenir deux fois la même clé, sinon la valeur pour cette clé est remplacée par la dernière valeur assignée à cette clé.

__Suppression__

Si on souhaite supprimer un élément d’un dictionnaire, on pourra encore une fois utiliser le mot-clé del.

```python
notes_eleves["Julien"]=13
print(notes_eleves) # {'Marie': 15, 'Thomas': 12, 'Julien': 13, 'Elise': 9, 'Samuel': 17, 'Julie': 9}
```

### c. Parcourir un dictionnaire
Parcourir un dictionnaire, c’est-à-dire itérer sur chaque élément de celui-ci, est possible soit par clés-valeurs, soit juste par les clés, soit juste par les valeurs. Pour cela, on utilisera une boucle ```for```.

__keys()__
Pour les dictionnaires, il existe une méthode, ```keys()```, qui retourne la liste de toutes les clés d’un dictionnaire. Il suffit ensuite d’y appliquer une boucle ```for``` pour parcourir cette liste.
```python
for cle in mon_dictionnaire.keys(): 
    print(cle)
```

Exemple:
```python
for prenom in notes_eleves.keys():
    print(prenom)
```

__values()__
De même, il existe une méthode, ```values()```, qui retourne la liste de toutes les valeurs d’un dictionnaire. Il suffit ensuite d’y appliquer une boucle ```for``` pour parcourir cette liste de valeurs.

```python
for valeur in mon_dictionnaire.values(): 
    print(valeur)
```

__items()__
Et enfin, si on veut parcourir simultanément les clés et les valeurs, on utilise la méthode items(), qui va renvoyer une liste contenant des tuples de couples clé-valeur.

```for cle,valeur in mon_dictionnaire.items(): 
    print(cle,valeur)
```

````python
notes_eleves.items() # dict_items([('Marie', 15), ('Thomas', 12), ('Julien', 13), ('Elise', 9), ('Samuel', 17)])
```

Exemple : 
```python
for cle,valeur in notes_eleves.items():
    print(cle, valeur)
```

Marie 15

Thomas 12

Julien 13

Elise 9

Samuel 17
