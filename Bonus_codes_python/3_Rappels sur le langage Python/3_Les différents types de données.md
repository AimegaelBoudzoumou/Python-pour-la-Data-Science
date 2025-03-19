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
