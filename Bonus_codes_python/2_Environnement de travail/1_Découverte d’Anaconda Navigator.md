### Ennoncé 1:
Écris une fonction en Python nommée ```lister_librairies``` qui prend en entrée une liste de librairies Python et retourne une chaîne de caractères contenant toutes les librairies séparées par une virgule. Par exemple, si la fonction reçoit la liste ```["Numpy", "Matplotlib", "Pandas"]```, elle doit retourner la chaîne ```"Numpy, Matplotlib, Pandas"```.

Assure-toi que ta fonction gère le cas où la liste est vide en retournant une chaîne vide.

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
