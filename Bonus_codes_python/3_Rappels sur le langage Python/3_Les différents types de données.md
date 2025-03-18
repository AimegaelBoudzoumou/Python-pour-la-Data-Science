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

