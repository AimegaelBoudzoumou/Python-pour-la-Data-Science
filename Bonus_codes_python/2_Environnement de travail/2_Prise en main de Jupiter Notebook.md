```python
def verifier_port(port_number):
    """vérifier port
    
    Cette fonction permet de vérifier si le port pour Jupyter Notebook est valide
    Argument : un nombre entier positif, les autres types types ne sont pas acceptés
    Retourne une chaîne de caractères
    """
    
    if (isinstance(port_number, int)):
        
        valid_ports = {8888, 8889, 8890}
        
        if port_number in valid_ports:
            
            return "Port valide"
            
        else:
            
            return "Port invalide"
    
    else:
        
        return "Port invalide"
```

```python
def renommer_notebook(actual_notebook_name, desire_notebook_name):
    """Cette fonction doit retourner le nouveau nom du notebook en respectant les bonnes 
    pratiques, c'est-à-dire en remplaçant tous les espaces par des underscores et en 
    ajoutant l'extension ".ipynb" à la fin du nom.
    La méthode strip() suffit à vérifier si la chaîne est vide ou ne contient que des espaces.
    
    Arguments : prend en entrée le nom actuel d'un notebook (sous forme de chaîne) 
    et un nouveau nom désiré (également sous forme de chaîne)
    
    Retourne le nouveau nom du notebook qui est une chaîne de caractères
    
    """
    
    if not desire_notebook_name.strip():
        return "Untitled.ipynb"
    
    return desire_notebook_name.replace(' ', '_') + ".ipynb"
```

```python
def generer_raccourcis(raccouris):
    """Cette fonction prend en entrée une liste de raccourcis-clavier (sous forme de chaîne) et retourne un dictionnaire où chaque raccourci est associé à une description de son action
     Argument : une liste non vide
     Retourne un dictionnaire contenant comme clé une raccourci clavier et comme valeur son explication
     """
     
     # dictionnaire de base contenant les clé (raccourcis-clavier) et valeurs (significations des raccourcis-clavier)
     dictionnaire_de_base = {
        "B": "insère une cellule après la cellule sélectionnée",
        "A": "insère une cellule avant celle-ci",
        "F": "ouvre une fenêtre qui permet de chercher-remplacer du texte dans l’ensemble de votre notebook"
    }
    
    # dictionnaire à retourer peu importe la situation :
    dictionnaire_resultat = {}
    
    # vérifier que la liste raccouris n'est pas vide:
    if raccouris:
        for element in raccouris:
            # on vérifie que l'élément est une chaîne de caractères
            if isinstance(element, str):
                if element in dictionnaire_de_base:
                    dictionnaire_resultat[element] = dictionnaire_de_base[element]

    return dictionnaire_resultat

    """
    Remarque: Pensez à gérer le cas où la liste contient des éléments qui ne sont pas des chaînes de caractères,
    comme vous l'avez fait, mais vous pourriez simplifier cette vérification en utilisant une compréhension de dictionnaire.

    Ressources sur la notion de "compréhension de dictionnaire": https://www.expertpython.fr/post/ma%C3%AEtriser-les-compr%C3%A9hensions-en-python-listes-tuples-et-        dictionnaires#:~:text=La%20compr%C3%A9hension%20de%20dictionnaire%20est,des%20%C3%A9l%C3%A9ments%20d%27un%20dictionnaire. 
    """
```
