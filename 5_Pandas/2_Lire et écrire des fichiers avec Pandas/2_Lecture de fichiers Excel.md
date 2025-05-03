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
import pandas as pd
donnees_excel=pd.read_excel(r"Python Data Science\JO_Dataset\120-years-of-olympic-history-athletes-and-results.xlsx")
donnees_excel.head()
```

![image](https://github.com/user-attachments/assets/4f9a443c-bf07-498a-ac2c-c28cab1e6ab6)


Attention, si vous rencontrez une erreur lors de cette commande, dont la dernière ligne est : ```ImportError : Missing optional dependency ’xlrd’``` ..., veuillez procéder de la manière suivante :

Lancez le logiciel __Anaconda Powershell Prompt__ puis tapez la commande ```pip install xlrd``` pour installer le package xlrd, qui réglera ce problème.

Si on souhaite lire la deuxième feuille de ce fichier, on utilise l’option ```sheet_name``` avec le nom de la feuille qui nous intéresse.

```python
import pandas as pd
donnees_excel_feuil2=pd.read_excel(r"Travaux_2025\Python Data Science\JO_Dataset\120-years-of-olympic-history-athletes-and-results.xlsx", sheet_name="Feuille2")
donnees_excel_feuil2.head()
```

![image](https://github.com/user-attachments/assets/1cbe89bc-808d-4ab3-a9fe-9851071b846a)
