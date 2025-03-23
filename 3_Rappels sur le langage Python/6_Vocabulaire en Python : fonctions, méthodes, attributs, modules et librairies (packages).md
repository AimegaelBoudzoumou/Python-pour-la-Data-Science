# Vocabulaire en Python : fonctions, méthodes, attributs, modules et librairies (packages)

## 1. Fonctions
Une fonction est une portion de code à l’intérieur d’un fichier qui permet d’effectuer des tâches bien précises et ce de manière répétée.

Une fonction attend généralement quelque chose en entrée, cela peut être un nombre, une chaîne de caractères, ou une structure de données plus complexe comme une liste, un dictionnaire, etc. Une fois que cette fonction est appelée par Python, le code qu’elle contient est exécuté sur ce que Python lui donne en entrée et, en sortie, on a généralement un résultat différent de ce qui a été donné en entrée. Le nom de la fonction définit généralement ce qu’elle fait.

Python possède un nombre conséquent de fonctions "built-in", c’est-à-dire de fonctions intégrées au langage Python, qui sont présentes dès l’installation du langage. Par exemple, la fonction ```print()```, qui veut dire afficher en français, est disponible automatiquement avec Python et permet d’afficher ce qu’on lui donne en entrée. Une fonction a donc un nom, puis elle est suivie de parenthèses, à l’intérieur desquelles on lui donne les arguments, les objets, que l’on veut qu’elle prenne en entrée pour pouvoir faire son traitement.

Syntaxe:

```
ma_fonction(objet1, objet2, ...)
```

Une fonction peut prendre plusieurs arguments, plusieurs options. Il y a les arguments obligatoires, nécessaires à son bon fonctionnement, et les arguments optionnels, si on souhaite que la fonction se comporte différemment de son comportement par défaut.

Pour savoir ce qu’une fonction prend comme arguments, vous pouvez utiliser la fonction ```help()```, une autre fonction "built-in" de Python. Il suffit de lui donner le nom de la fonction et elle affiche l’aide de la fonction donnée.

Syntaxe :
```python
help(ma_fonction) 
```

```python
help(print)
```

```
Help on built-in function print in module builtins:

print(*args, sep=' ', end='\n', file=None, flush=False)
    Prints the values to a stream, or to sys.stdout by default.

    sep
      string inserted between values, default a space.
    end
      string appended after the last value, default a newline.
    file
      a file-like object (stream); defaults to the current sys.stdout.
    flush
      whether to forcibly flush the stream.
```

On voit divers arguments, dont x```end```, qui permet de spécifier le caractère à la fin du texte affiché par ```print()``` : c’est par défaut un ```\n```, qui correspond à un retour à la ligne. Pour l’exemple, mettons le caractère ```b``` comme fin de ligne.
```python
print(12, end="b") # 12b
```
Les différents arguments sont séparés par des virgules, ce qui fait qu’une fonction peut être très finement paramétrée grâce à différents arguments.

## 2. Méthodes
Une méthode est une fonction qui appartient à une classe. Une fonction n’est pas liée à une classe d’objet (liste, tuple, dictionnaire...), alors qu’une méthode, si. Par exemple, un objet de type ```list``` en Python possède ses méthodes, de même que les dictionnaires possèdent leurs méthodes. Ces méthodes permettent de manipuler facilement les objets de la classe à laquelle elles appartiennent. Par exemple, pour les listes, il existe la méthode ```insert()```, qui permet d’insérer un élément dans la liste, la méthode ````count()```, qui permet de compter le nombre d’éléments dans une liste, etc.

Syntaxe :
```python
ma_liste.ma_methode()
```

Contrairement à la fonction, où on donne l’objet entre parenthèses comme argument, ici, on précède le nom de la méthode par le nom de l’objet sur lequel on souhaite effectuer le traitement. Et si on souhaite ajouter des options, celles-ci seront données entre parenthèses.

## 3. Attributs
Les attributs sont des variables associées à une classe d’objets. Tout comme pour les méthodes, les classes d’objets possèdent un ensemble d’attributs spécifiques. Les attributs permettent d’accéder à des informations concernant un objet : une liste, un tuple... Par exemple, les listes ont un ensemble d’attributs.

Pour utiliser un attribut, la syntaxe est la suivante :

```python
ma_liste.mon_attribut
```

Contrairement à la méthode, qui est suivie de parenthèses permettant de donner des arguments supplémentaires, l’attribut, lui, ne l’est pas. Il s’agit juste d’un nom de variable qui permet de récupérer des informations sur un objet. Par exemple, la classe ```ndarray``` (les tableaux NumPy, que nous verrons plus tard) possède un ensemble d’attributs très pratiques permettant d’avoir des informations sur le tableau. Par exemple, ```mon_ndarray.size``` permet d’afficher le nombre d’éléments dans le tableau, grâce à l’attribut ```size```.

## 4. Modules
ase lors de l’installation de Python. Ces fonctions sont fournies automatiquement car ce sont des fonctions essentielles et très utilisées, comme la fonction ```print()```, pour ne citer qu’elle. Les fonctions moins courantes sont regroupées dans des modules qu’il faut importer pour pouvoir utiliser ces fonctions.


Un module est un ensemble de fichiers ```.py``` (extension de Python) contenant des fonctions, des classes ou encore des variables pouvant être appelées dans votre code. Ainsi, lorsque vous développez votre programme, vous pouvez importer des modules afin de pouvoir utiliser les fonctions qu’ils contiennent.

De même, si votre programme devient conséquent, il est recommandé de ranger vos fonctions dans des fichiers ```.py``` séparés, que vous appellerez dans votre programme principal. Ces fichiers ```.py``` dans lesquels vous rangez vos fonctions sont des modules Python. Un module a un nom, et ce nom n’est autre que le texte qui se trouve avant l’extension ```.py```. Ainsi, si on veut importer dans son programme le code contenu dans le fichier ```mon_module.py```, on importera le module avec le nom ```mon_module```.

Pour accéder à ces modules, il faut utiliser le mot-clé import.

Syntaxe :
```python
import mon_module
```

Généralement, les importations de modules se font en début de programme, et une fois qu’ils sont importés, l’ensemble des fonctions sont disponibles et utilisables dans votre programme. Comme pour les fonctions, il existe un ensemble de modules "built-in", disponibles de base avec Python. Les plus populaires sont les modules math, random, etc.

Ces modules contiennent donc des fonctions. Une fois les modules importés, si vous souhaitez utiliser une fonction de ce module, il suffit d’utiliser la syntaxe suivante :
```python
import mon_module 
mon_module.ma_fonction()
```

Si le nom du module est trop long, il est possible de créer un alias de ce module pour raccourcir son nom.
```python
import mon_module as m 
m.ma_fonction()
```

Enfin, si on souhaite ne plus utiliser le nom du module avant le nom de la fonction, il faut utiliser la syntaxe suivante :

```python
from mon_module import ma_fonction 
ma_fonction()
```

De cette manière, on définit ```ma_fonction``` dans l’espace de noms de notre programme et à partir de ce moment-là, il n’est plus nécessaire de mettre le nom du module avant le nom de la fonction.



## 5. Librairies (packages)
Une librairie (ou package) peut être vue comme un dossier contenant un ensemble de modules, un ensemble de fichiers ```.py```. Une librairie a une application particulière et regroupe donc l’ensemble des modules permettant de répondre à cette application. Par exemple, on peut créer une librairie pour faire du calcul scientifique, des graphiques, de la manipulation de données, etc. Ces librairies contiendront un ensemble de modules, et donc de fonctions, méthodes, classes, etc. permettant d’effectuer ces tâches précises.

Ces librairies sont créées et mises à disposition pour faciliter la programmation en Python, mais aussi pour nous éviter d’avoir à réécrire du code utilisé par un grand nombre de personnes. Au début de ce livre, nous avons installé la distribution Anaconda, qui permet d’installer Python et un ensemble de librairies dédiées à la Data Science, comme Pandas pour la manipulation de tableaux (dataframes) ou encore Matplotlib pour la visualisation de données. Vous le verrez tout au long de ce livre, ces librairies vont nous faciliter grandement la vie. Elles nous permettront d’utiliser des fonctions qui font des choses très complexes, en leur donnant juste nos objets en entrée et en récupérant le résultat à la fin, sans rien avoir à faire de plus !
