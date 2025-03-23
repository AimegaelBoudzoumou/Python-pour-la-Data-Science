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

## 3. Attributs

## 4. Modules

## 5. Librairies (packages)
