### Ennoncé 1:
Écris une fonction en Python nommée ```convertir_type``` qui prend un nombre en entrée (sous forme d'entier ou de float) et retourne une chaîne de caractères indiquant son type. Si le nombre est un entier, la fonction doit retourner "int". Si le nombre est un float, elle doit retourner "float". La fonction doit également afficher le type d'origine en utilisant la fonction ```type()```. Par exemple, si la fonction reçoit 3 comme entrée, elle doit retourner "int", et si elle reçoit ```3.5```, elle doit retourner "float".

```python
def convertir_type(nombre):
    """Cette fonction prend un nombre en entrée (sous forme d'entier ou de float) 
    et retourne une chaîne de caractères indiquant son type.
    
    Argument : un nombre (sous forme d'entier ou de float)
    
    Retourne une chaîne de caractères indiquant le type du nombre ci-dessus.
    En cas d'entrée non valide (ie ni int, ni float), c'est ce message qui est retoruné :
    "Type non pris en charge : car la fonction attend soit int, soit float"
    """
    
    if isinstance(nombre, int):
        print(type(nombre))
        return 'int'
    elif isinstance(nombre, float):
        print(type(nombre))
        return 'float'
    else:
        return "Type non pris en charge : car la fonction attend soit int, soit float"
```

### Ennoncé 2:
Écris une fonction en Python nommée ```verifier_comparaison``` qui prend deux nombres en entrée et un opérateur de comparaison sous forme de chaîne (par exemple, ">", "<", "==", ">=", "<="). La fonction doit évaluer la comparaison entre les deux nombres selon l'opérateur fourni et retourner un booléen (True ou False) en fonction du résultat. Si l'opérateur fourni n'est pas valide, la fonction doit retourner la chaîne "Opérateur invalide". Par exemple, pour les entrées ```(3, 5, "<")```, la fonction doit retourner ```True```, et pour ```(3, 5, ">=")```, elle doit retourner ````False```.
```python
def verifier_comparaison(nombre1, nombre2, operateur):
    """ Cette fonction évalue la comparaison entre deux nombres selon l'opérateur fourni 
    
    Arguments : deux nombres en entrée et un opérateur de comparaison sous forme de chaîne
    
    Retourner un booléen (True ou False) en fonction du résultat.
    """
    
    # Si l'opérateur fourni n'est pas valide, la fonction doit retourner 
    # la chaîne "Opérateur invalide"
    operateurs_valides = {">", "<", "==", ">=", "<="}
    
    if operateur not in operateurs_valides:
        return "Opérateur invalide"
    
    if operateur == ">":
        return nombre1 > nombre2
    elif operateur == "<":
        return nombre1 < nombre2
    elif operateur == "==":
        return nombre1 == nombre2
    elif operateur == ">=":
        return nombre1 >= nombre2
    elif operateur == "<=":
        return nombre1 <= nombre2
    else:
        return "Opérateur invalide"
    
    """
    Pour améliorer la lisibilité, vous pourriez envisager d'utiliser un dictionnaire 
    pour mapper les opérateurs à leurs fonctions correspondantes, 
    ce qui pourrait rendre le code plus concis.
    """
```

### Ennoncé 3:
Écris une fonction en Python nommée ```concatener_textes``` qui prend en entrée deux chaînes de caractères et retourne leur concaténation. Si l'une des entrées n'est pas une chaîne de caractères, la fonction doit lever une exception de type ```ValueError``` avec le message "Les deux entrées doivent être des chaînes de caractères". Par exemple, si la fonction reçoit les entrées "Bonjour" et " le monde", elle doit retourner "Bonjour le monde". Si la fonction reçoit "15" et 2, elle doit lever l'exception mentionnée.

```python
def concatener_textes(chaine1, chaine2):
    """Cette fonction prend en entrée 
    deux chaînes de caractères et retourne leur concaténation.
    Si l'une des entrées n'est pas une chaîne de caractères, 
    la fonction doit lever une exception de type ValueError 
    avec le message "Les deux entrées doivent être des chaînes de caractères".
    Note : Une erreur ValueError en Python est une exception qui survient lorsqu'une 
    opération reçoit un argument ayant le bon type mais une valeur inappropriée.
    
    Arguments : deux chaînes de caractères
    
    Retourne une chaîne de caractères
    """
        
    if (isinstance(chaine1, str) and isinstance(chaine2, str)):
        return chaine1 + chaine2
    else:
        raise ValueError("Les deux entrées doivent être des chaînes de caractères")
    
    """
    Pense à ajouter des tests supplémentaires pour vérifier 
    le comportement de la fonction avec des chaînes vides ou des espaces.
    """
```
