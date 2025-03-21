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
