```python
def lister_librairies(liste_librairies):
    """Cette fonction prend en entrée une liste de librairies Python et 
    retourne une chaîne de caractères contenant toutes les librairies 
    séparées par une virgule.
    
    Argument : une liste de librairies
    
    Retourne une chaîne de caractères contenant toutes les librairies
    """
    
    if not liste_librairies:
        return ""
    else:
        return (", ").join(liste_librairies)
```
