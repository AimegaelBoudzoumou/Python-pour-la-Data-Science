# Lecture de fichiers Excel

Pour lire un fichier Excel, c’est-à-dire un fichier au format XLSX ou XLS, il suffit d’utiliser la fonction ```read_excel()``` de Pandas.

```python
import pandas as pd 
fichier_excel=pd.read_excel('mon_fichier.xlsx')
```

Par défaut, la fonction ```read_excel()``` lit la première feuille Excel du fichier qu’on lui donne. 

Si on souhaite importer une autre feuille, il faut donner le nom de la feuille à l’option ```sheet_name```, qui signifie ’nom de la feuille’, en français.

```python
import pandas as pd  
fichier_excel=pd.read_excel('mon_fichier.xlsx',  
sheet_name="Nom_de_la_feuille")
```

À chaque fois, la structure de données créée sera un dataframe, contenant les données de la feuille Excel qui nous intéresse. 

Les autres options de cette fonction sont les mêmes que celles vues précédemment avec les fonctions ```read_table()``` et ```read_csv()```, comme les options ```header```, ```names```, ```index_col```, ```usecols```, ```squeeze```, ou encore ```dtype```.

__Pratiquons :__

En téléchargement avec ce livre, vous pouvez récupérer le fichier "120-years-of-olympic-history-athletes-and-results.xlsx". 

Ce fichier contient une première feuille avec les données de JO et une deuxième feuille factice.

Pour lire la première feuille du fichier Excel, le code est le suivant :

```python

```
