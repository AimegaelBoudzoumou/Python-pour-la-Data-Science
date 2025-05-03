# Lecture de fichiers au format JSON

Voici un aperçu d'un fichier Json :

![image](https://github.com/user-attachments/assets/10248d49-8dbf-4074-959f-d14804769a36)

Pour expliquer brièvement ce format, l’ensemble des données sont stockées entre crochets ```[]```. Puis, chaque individu ou observation est stocké entre accolades ```{}```, ces accolades pouvant être comparées aux lignes d’un tableau classique. Enfin, chaque accolade contient l’ensemble des informations (des colonnes) de l’individu/observation sous forme de clés-valeurs séparées par des virgules. Chaque couple clé-valeur représente une colonne de la ligne.

La librairie Pandas propose une fonction appelée ```read_json()``` qui permet de lire un fichier au format JSON.

```python
import pandas as pd 
pd.read_json("mon_fichier.json") 
```

__Pratiquons__
```python
import pandas as pd
donnees=pd.read_json(r"C:\Users\chris\Documents\Travaux_2025\Python Data Science\employees.json")
donnees.head()
```
![image](https://github.com/user-attachments/assets/c1955259-ca41-42b8-b9b6-66ad56dc556d)

