# Importation des données à partir d’une base de données

Si vous souhaitez importer des données à partir d’une base de données plutôt que d’un fichier plat comme les formats vus précédemment, c’est possible.

Par exemple, pour une base de données SQLite, la syntaxe générale sera la suivante :

```python
import pandas as pd 
import sqlite3 
connexion = sqlite3.connect('base_de_donnees.db') 
requete = "SELECT * FROM TABLES;" 
resultats = pd.read_sql(requete, con=connexion) 
resultats.head() 
```

Pour l’exemple, sachez que cette base de données contient onze tables, dont une table contenant les informations au sujet des employés d’une entreprise. Imaginons que nous ayons envie de récupérer les informations de l’ensemble des employés de la base de données afin de les stocker dans un dataframe pour les analyser, le code serait le suivant.

```python
import pandas as pd
import sqlite3
connexion = sqlite3.connect(r"Python Data Science\chinook.db")
requete = "SELECT * FROM employees;"
resultats = pd.read_sql(requete, con=connexion)
resultats.head()
```
![image](https://github.com/user-attachments/assets/c4a0852a-f89e-49f2-92ca-d28dd5f5e85a)
