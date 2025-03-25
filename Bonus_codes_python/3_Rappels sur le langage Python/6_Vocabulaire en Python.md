### Ennoncé 1:
Écris une fonction en Python nommée afficher_message qui prend une chaîne de caractères en entrée et 
un argument optionnel fin (avec une valeur par défaut de la chaîne de caractères \n). 
La fonction doit afficher le message donné en entrée suivi du caractère spécifié par l'argument fin. 
Par exemple, si la fonction reçoit "Bonjour" et que fin est égal à "!", elle doit afficher "Bonjour!". 
Si fin n'est pas fourni, elle doit simplement afficher "Bonjour" suivi d'un retour à la ligne.
```python
def afficher_message(message, fin="\n"):
    """Cette fonction doit afficher le message donné en entrée suivi 
    du caractère spécifié par l'argument fin
    
    Arguments : une chaîne de caractères en entrée et 
    un argument optionnel fin (avec une valeur par défaut de la chaîne de caractères \n)
    
    Affiche le message donné en entrée suivi du caractère spécifié par l'argument fin
    """
    
    if isinstance(message, str):
        print(message + fin)
    else:
        print("Le message doit être une chaîne de caractères")
    """
    Remarques :
    1. La vérification du type de message est une bonne pratique, mais il serait préférable de lever une exception plutôt que d'afficher un message d'erreur dans 
    la fonction. Cela permettrait à l'utilisateur de gérer les erreurs de manière plus appropriée.
    2. Pense à ajouter des tests supplémentaires pour couvrir d'autres cas, comme des chaînes vides ou des caractères spéciaux.
    """
```

### Ennoncé 2:
Écris une classe en Python nommée Voiture qui possédera les attributs suivants : marque, modele et annee. 
Crée un constructeur qui initialisera ces attributs lors de la création d'une instance de la classe. 
Ajoute également une méthode description qui retourne une chaîne de caractères décrivant la voiture au format suivant : 
"Marque: [marque], Modèle: [modèle], Année: [année]". Par exemple, si la voiture est une Toyota Corolla de l'année 2020, 
la méthode doit retourner "Marque: Toyota, Modèle: Corolla, Année: 2020". Dans le code, 
n'oublie pas que les attributs ne doivent pas être suivis de parenthèses lors de leur utilisation.
```python
class Voiture():
    """Cette classe possédera les attributs suivants : marque, modele et annee. 
    On y Crée un constructeur qui initialisera ces attributs lors de la création d'une instance 
    de la classe. 
    On y Ajoute également une méthode description qui retourne une chaîne de caractères 
    décrivant la voiture au format suivant : "Marque: [marque], Modèle: [modèle], Année: [année]".
    
    Retorune doit retourner la chaîne de caractères : "Marque: Toyota, Modèle: Corolla, Année: 2020".
    
    Pour instancer la classe Voiture, faire : voiture = Voiture("Toyota", "Corolla", "2020")
    
    Pour appeler la méthode description, faire : voiture.description()
    """
    
    
    def __init__(self, marque, modele, annee):
        self.marque = marque
        self.modele = modele
        self.annee  = annee
    
    def description(self):
        return f"Marque: {self.marque}, Modèle: {self.modele}, Année: {self.annee}"
```

### Ennoncé 3:
Écris une fonction en Python nommée creer_librairie qui prend en entrée un nom de librairie (sous forme de chaîne) 
et une liste de modules (sous forme de liste de chaînes). La fonction doit retourner un dictionnaire 
où la clé est le nom de la librairie et la valeur est une liste de modules. Par exemple, 
si la fonction reçoit "CalculScientifique" et la liste ["module1", "module2", "module3"], 
elle doit retourner {"CalculScientifique": ["module1", "module2", "module3"]}. Si la liste de modules est vide, 
la fonction doit retourner un dictionnaire avec le nom de la librairie et une valeur de liste vide.
```python
```
